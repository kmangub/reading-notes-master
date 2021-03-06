# Django Forms

## Overview

Forms are a great way to collect data from users by creating, updating, and deleting. Below is an example of forms:

```
<form action="/team_name_url/" method="post">
    <label for="team_name">Enter name: </label>
    <input id="team_name" type="text" name="name_field" value="Default name for team.">
    <input type="submit" value="OK">
</form>
```

In Django, we are using similar techniques. The main points that Django handles are:

1. Display the default form the first time it is requested by the user.

2. Receive data from a submit request and bind it to the form.

3. Clean and validate the data.

4. If any data is invalid, re-display the form, this time with any user populated values and error messages for the problem fields.

5. If all data is valid, perform required actions (e.g. save the data, send an email, return the result of a search, upload a file, etc.)

6. Once all actions are complete, redirect the user to another page.

## Create Form 

To create a form, we need to create a `Form` class. This class will handle the layout, display widgets, labels, initial values, valid values, and (once validated) the error messages associated with invalid fields.

Next, we need to declare the form. Data is stored in the `forms.py` and import the forms library. We also need to select the appropriate type of form fields, such as `CharField` and `DateField`.

The forms can be validated using `clean_<fieldname>()` and returning the value at the end of the function. Below is an example:

```
import datetime

from django import forms
from django.core.exceptions import ValidationError
from django.utils.translation import ugettext_lazy as _

class RenewBookForm(forms.Form):
    renewal_date = forms.DateField(help_text="Enter a date between now and 4 weeks (default 3).")

    def clean_renewal_date(self):
        data = self.cleaned_data['renewal_date']

        # Check if a date is not in the past.
        if data < datetime.date.today():
            raise ValidationError(_('Invalid date - renewal in past'))

        # Check if a date is in the allowed range (+4 weeks from today).
        if data > datetime.date.today() + datetime.timedelta(weeks=4):
            raise ValidationError(_('Invalid date - renewal more than 4 weeks ahead'))

        # Remember to always return the cleaned data.
        return data
```

## URL Configuration 

In the `urls.py` file, we add a path in `urlpatterns`. For instance, 

```
urlpatterns += [
    path('book/<uuid:pk>/renew/', views.renew_book_librarian, name='renew-book-librarian'),
]
```

The URL configuration will redirect URLs with the format `/catalog/book/<bookinstance_id>/renew/` to the function named `renew_book_librarian()` in `views.py`, and send the BookInstance id as the parameter named `pk`. The pattern only matches if `pk` is a correctly formatted uuid.

## View

Our view has to render the form by defualt and would have to re-render when the data is invalid and if the data is valid, then the form will proceed to process the data. The form will use a POST request approach. 

```
import datetime

from django.shortcuts import render, get_object_or_404
from django.http import HttpResponseRedirect
from django.urls import reverse

from catalog.forms import RenewBookForm

def renew_book_librarian(request, pk):
    book_instance = get_object_or_404(BookInstance, pk=pk)

    # If this is a POST request then process the Form data
    if request.method == 'POST':

        # Create a form instance and populate it with data from the request (binding):
        form = RenewBookForm(request.POST)

        # Check if the form is valid:
        if form.is_valid():
            # process the data in form.cleaned_data as required (here we just write it to the model due_back field)
            book_instance.due_back = form.cleaned_data['renewal_date']
            book_instance.save()

            # redirect to a new URL:
            return HttpResponseRedirect(reverse('all-borrowed') )

    # If this is a GET (or any other method) create the default form.
    else:
        proposed_renewal_date = datetime.date.today() + datetime.timedelta(weeks=3)
        form = RenewBookForm(initial={'renewal_date': proposed_renewal_date})

    context = {
        'form': form,
        'book_instance': book_instance,
    }

    return render(request, 'catalog/book_renew_librarian.html', context)
```

We import our forms along with the following methods and objects:

- `get_object_or_404()`: Returns a specified object from a model based on its primary key value, and raises an Http404 exception (not found) if the record does not exist.
- `HttpResponseRedirect`: This creates a redirect to a specified URL (HTTP status code 302).
- `reverse()`: This generates a URL from a URL configuration name and a set of arguments. It is the Python equivalent of the url tag that we've been using in our templates.
- `datetime`: A Python library for manipulating dates and times.

We need to use the `render()` function to create the HTML page. 

## Template 

For the template, we need to extend the base template and refine the rest. It will look something like this:




```
{% raw  %}
{% extends "base_generic.html" %}

{% block content %}
  <h1>Renew: {{ book_instance.book.title }}</h1>
  <p>Borrower: {{ book_instance.borrower }}</p>
  <p{% if book_instance.is_overdue %} class="text-danger"{% endif %}>Due date: {{ book_instance.due_back }}</p>

  <form action="" method="post">
    {% csrf_token %}
    <table>
    {{ form.as_table }}
    </table>
    <input type="submit" value="Submit">
  </form>
{% endblock %}
{% endraw %}
```
