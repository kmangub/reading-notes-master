# Using Models

We can manage data and application access using **Models** , or Python Objects. When designing models, we need to be mindful about the information we are storing and when to separate models.

The relationships between models can differ and can be one to one (OneToOneField), one to many (ForeignKey) and many to many (ManyToManyField).

## Model Primer

Models are defined in the `models.py` and they include fields, methods, and metadata.

## Fields 

Fields represent a column of data that we want to store in our database tables. Here is an example:

```
my_field_name = models.CharField(max_length=20, help_text='Enter field documentation')
```

Where `CharField` contains numbers and letters, max value is 20 characters in the field, and `help_text`, which is the label showing what the user needs to type. 

A list of arguments can be found [here](https://docs.djangoproject.com/en/3.1/ref/models/fields/#field-options).

A list of field types can be found [here](https://docs.djangoproject.com/en/3.1/ref/models/fields/#field-types).

## Metadata

To declare metadata, we declare a class:

```
class Meta:
    ordering = ['-my_field_name']
```

We can use this to sort our models however we want. For example, if we want to sort a book in alphabetical order and then by the publication date, we would input the following:

```
ordering = ['title', '-pubdate']
```

We can also use the attribute `verbose_name`.

## Methods

Models can have methods. At a minimum, the models should have the class method `__str__()`. Another method is `get_absolute_url()`, which returns a URL for displaying indivifual model records on the website. An example is shown below:

```
def get_absolute_url(self):
    """Returns the url to access a particular instance of the model."""
    return reverse('model-detail-view', args=[str(self.id)])
```

## Model Management

We are able to create, update, or delete records after we defined the model classes.

For creating and modifying the records:

```
# Create a new record using the model's constructor.
record = MyModelName(my_field_name="Instance #1")

# Save the object into the database.
record.save()
```

For searching records, we use `objects.all()`. We can also use `filter()` to match a specific text or numeric fields.

A list of look-ups can be found [here](https://docs.djangoproject.com/en/3.1/ref/models/querysets/#field-lookups).

## Defining the LocalLibrary Models

We can start by navigating to or `models.py`, which will have the following:
```
from django.db import models

# Create your models here.
```

From here, we can extablish a Genre class:

```
class Genre(models.Model):
    """Model representing a book genre."""
    name = models.CharField(max_length=200, help_text='Enter a book genre (e.g. Science Fiction)')

    def __str__(self):
        """String for representing the Model object."""
        return self.name
```



# Django Admin

The Django admin application uses the models to build a site area that we can use to create, view, update, and delete records. The intention of the admin application is for internal use. 

## Registering models 

To register models, we open `admin.py` and it should contain this:

```
from django.contrib import admin

# Register your models here.
```

At the bottom of the file, we insert the following text:

```
from .models import Author, Genre, Book, BookInstance

admin.site.register(Book)
admin.site.register(Author)
admin.site.register(Genre)
admin.site.register(BookInstance)
```

## Creating a superuser

To log in to the admin site, we need to create an admin user with the *staff* status and it can be done with `manage.py`. 

To add a super user, input `python3 manage.py createsuperuser`. This will create a user in the database. Then we run the server using `python3 manage.py runserver`.

## Logging in and using the site

To log in, we navigate to our admin page. Typically it's the home page with `/admin` added to the end of the url. We enter the superuser username and password and we get directed to the admin page where we can add models and save the record. 

After the record has been saved, we can navigate to the home page and click on the model to view the saved information. We can add, edit, delete, and view models.