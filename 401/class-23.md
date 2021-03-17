# Docker

Docker enables us to isolate and run applications without having to switch over to our virtual environment. Docker is just **Linux Containers**, which is a type of virtualization, or a virtual type of something.

To start, we need to install the desktop app [here](https://www.docker.com/get-started).

Once the installation is complete, we need to verify that it's running version 19 or higher. We input this command and we should get a similar output:

```
$ docker --version

#Docker version 19.03.5, build 633a0ea
```

Docker Compose is something that is included with Mac and PC. The version should be at least `1.24.x`. We input the following in our terminal to find out the version:

```
$ docker-compose --version
docker-compose version 1.24.1, build 4667896b
```

To check if everything is running correctly, run the following commands in our terminal:

```
docker run hello-world
```

and 

```
docker info
```
To check the current image:

```
docker image ls
```

## Image and Containers

An **image** is a snapshot in time of what a project contains. 

A **container** is a running instance of the image.

A good analogy to remember is this:

- A Dockerfile is the recipe for a cake
- An image is a snapshot of the recipe at a given time
- A docker-compose.yml says how to make the cake
- And the container is the actual, baked cake


To build images, run the command 

```
image build .
```

and we'll get `successfully built` on the bottom.

Afterwards, we need to build a new django project. 

## Dockerize Django
We will replace the local dev environment using a `Dockerfile`, then create a `docker-compose.yml` file:

```
$ touch Dockerfile
$ touch docker-compose.yml
```
The the Dockerfile will contain the following:

```
# Dockerfile

# Python version
FROM python:3.7-alpine

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Set work directory
WORKDIR /code

# Install dependencies
COPY Pipfile Pipfile.lock /code/
RUN pip install pipenv && pipenv install --system

# Copy project
COPY . /code/
```
and our docker-compose.yml will have this:

```
# docker-compose.yml
version: '3.7'

services:
  web:
    build: .
    command: python /code/manage.py runserver 0.0.0.0:8000
    volumes:
      - .:/code
    ports:
      - 8000:8000
```

Instead of running multiple commands, we can run it with one:
```
$ docker-compose up --build
Creating network "djangoapp_default" with the default driver
Building webStep 1/6 : FROM python:3.7-alpine
...
Successfully built 047a6d848c5b
Successfully tagged djangoapp_web:latest
Recreating djangoapp_web_1 ... done
Attaching to djangoapp_web_1
web_1  | Performing system checks...
web_1  |
web_1  | Watching for file changes with StatReloader
web_1  | System check identified no issues (0 silenced).
web_1  |
web_1  | You have 17 unapplied migration(s). Your project may not work properly until you apply the migrati
ons for app(s): admin, auth, contenttypes, sessions.
web_1  | Run 'python manage.py migrate' to apply them.
web_1  | January 21, 2020 - 14:49:16
web_1  | Django version 3.0, using settings 'example_project.settings'
web_1  | Starting development server at http://0.0.0.0:8000/
web_1  | Quit the server with CONTROL-C.
```

# Library Website and API

Django REST Framework is added similar to a third party app.

In our `settings.py` file of our django project, add `rest_framework`:

```
# config/settings.py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    # 3rd party
    'rest_framework', # new

    # Local
    'books',
]
```
Then we create an `api` app.
```
$ python manage.py startapp api
```
and add to our installed apps:

```
# config/settings.py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    # 3rd party
    'rest_framework',

    # Local
    'books',
    'api', # new
]
```
> After creating our api app, we don't need to migrate since it's not using a database.

Update URLS:
```
# config/urls.py
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('api/', include('api.urls')), # new
    path('', include('books.urls')),
]
```

then create a urls.py file inside of our  api app:

```
$ touch api/urls.py
```

which will contain the following:

```
# api/urls.py
from django.urls import path
from .views import BookAPIView

urlpatterns = [
    path('', BookAPIView.as_view()),
]
```

Update `views.py` file:
```
# api/views.py
from rest_framework import generics

from books.models import Book
from .serializers import BookSerializer


class BookAPIView(generics.ListAPIView):
    queryset = Book.objects.all()
    serializer_class = BookSerializer
```

## Serializers
A serializer moves data into a format, like JSON, and is shown at the API endpoint.

This will be created within our API app:

```
$ touch api/serializers.py
```

and it will contain the following:

```
# api/serializers.py
from rest_framework import serializers

from books.models import Book


class BookSerializer(serializers.ModelSerializer):
    class Meta:
        model = Book
        fields = ('title', 'subtitle', 'author', 'isbn')
```

## cURL

To see what the endpoint looks like, run the server:

```
$ python manage.py runserver
```

Then open a second terminal to access the API. Run this command:

```
$ curl http://127.0.0.1:8000/api/
[  
   {  
      "title":"Django for Beginners",
      "subtitle":"Build websites with Python and Django",
      "author":"William S. Vincent",
      "isbn":"978-198317266"
   }
]
```

## Browsable API

Input `http://127.0.0.1:8000/api/` in our browser. This provides a visualization. To get the raw JSON, click "GET" on the top right and select "json".
