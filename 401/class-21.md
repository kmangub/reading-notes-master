# Custom User

Creating a custom user follows the same steps as creating an application on Django. The only thing is we have to hold off on running `migrate` to configure our database. There are two ways to create a custom user: `AbstractUser` and `AbstractBaseUser`. We will focus on `AbstractUser`.

To create our initial custom user model, we need to follow these four steps:

1. update config/settings.py
2. create a new CustomUser model
3. create new UserCreation and UserChangeForm
4. update the admin

In our `settings.py`, we need to add accounts under installed apps. We also need to add `AUTH_USER_MODEL` config. So,

```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'accounts', # new
]
...
AUTH_USER_MODEL = 'accounts.CustomUser' # new
```

Next, we will go to our `models.py` file and add in a new class called `CustomUser`.

```
from django.contrib.auth.models import AbstractUser
from django.db import models

class CustomUser(AbstractUser):
    pass
    # add additional fields in here

    def __str__(self):
        return self.username
```

Afterwards, we need to create a file inside of our app called `forms.py` and inside, we will paste the following code:

```
from django import forms
from django.contrib.auth.forms import UserCreationForm, UserChangeForm
from .models import CustomUser

class CustomUserCreationForm(UserCreationForm):

    class Meta:
        model = CustomUser
        fields = ('username', 'email')

class CustomUserChangeForm(UserChangeForm):

    class Meta:
        model = CustomUser
        fields = ('username', 'email')
```

Last, we will update our `admin.py` with the following changes:

```
# accounts/admin.py
from django.contrib import admin
from django.contrib.auth.admin import UserAdmin

from .forms import CustomUserCreationForm, CustomUserChangeForm
from .models import CustomUser

class CustomUserAdmin(UserAdmin):
    add_form = CustomUserCreationForm
    form = CustomUserChangeForm
    model = CustomUser
    list_display = ['email', 'username',]

admin.site.register(CustomUser, CustomUserAdmin)
```
After we make those changes, we will run our migration commands:

```
(accounts) $ python manage.py makemigrations accounts
(accounts) $ python manage.py migrate
```
## Templates/Views/URLs

Let's start by making additions to our `settings.py`. First we need to link our templates directory, then we need to add the following lines on the bottom:

```
LOGIN_REDIRECT_URL = 'home'
LOGOUT_REDIRECT_URL = 'home'
```

In the templates folder, make a `base.html` and `home.html`.

Create a directory called `registration` in the templates folder and inside that folder, make a `login.html` and a`signup.html`. 

### base.html

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>{% block title %}Django Auth Tutorial{% endblock %}</title>
</head>
<body>
  <main>
    {% block content %}
    {% endblock %}
  </main>
</body>
</html>
```

### home.html

```
{% extends 'base.html' %}

{% block title %}Home{% endblock %}

{% block content %}
{% if user.is_authenticated %}
  Hi {{ user.username }}!
  <p><a href="{% url 'logout' %}">Log Out</a></p>
{% else %}
  <p>You are not logged in</p>
  <a href="{% url 'login' %}">Log In</a> |
  <a href="{% url 'signup' %}">Sign Up</a>
{% endif %}
{% endblock %}
```

### registration/login.html

```
{% extends 'base.html' %}

{% block title %}Log In{% endblock %}

{% block content %}
<h2>Log In</h2>
<form method="post">
  {% csrf_token %}
  {{ form.as_p }}
  <button type="submit">Log In</button>
</form>
{% endblock %}
```

### registration/signup.html

```
{% extends 'base.html' %}

{% block title %}Sign Up{% endblock %}

{% block content %}
<h2>Sign Up</h2>
<form method="post">
  {% csrf_token %}
  {{ form.as_p }}
  <button type="submit">Sign Up</button>
</form>
{% endblock %}
```

### /urls.py

```
from django.contrib import admin
from django.urls import path, include
from django.views.generic.base import TemplateView

urlpatterns = [
    path('', TemplateView.as_view(template_name='home.html'), name='home'),
    path('admin/', admin.site.urls),
    path('accounts/', include('accounts.urls')),
    path('accounts/', include('django.contrib.auth.urls')),
]
```

Create a `urls.py` inside of our app.

### app/urls.py
```
from django.urls import path
from .views import SignUpView

urlpatterns = [
    path('signup/', SignUpView.as_view(), name='signup'),
]
```

### app/views.py
```
from django.urls import reverse_lazy
from django.views.generic.edit import CreateView

from .forms import CustomUserCreationForm

class SignUpView(CreateView):
    form_class = CustomUserCreationForm
    success_url = reverse_lazy('login')
    template_name = 'registration/signup.html'
```

From here, we can run the server and sign up to create users.

# DjangoX

DjangoX is an open-source Django starter framework that includes a custom user model, email/password by default instead of username/email/password, social authentication, and more. We can find more information here: https://github.com/wsvincent/djangox