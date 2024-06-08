# Installation

Django Ledger is a [Django](https://www.djangoproject.com/) application. If you haven't, you need working knowledge of
Django and a working Django project before you can use Django Ledger. A good place to start
is [here](https://docs.djangoproject.com/en/4.2/intro/tutorial01/#creating-a-project).

Make sure you refer to the django version you are using.

The easiest way to start is to use the zero-config Django Ledger starter template. See
details [here](https://github.com/arrobalytics/django-ledger-starter). Otherwise, you may create your
project from scratch.

To create a new Django Ledger project:

* Make sure you have the latest version of python [here](https://www.python.org/) (recommended).

* Install Django:

```shell
pip install django
```

* Install Python [Pipenv](https://pipenv.pypa.io/en/latest/) (python package manager):

```shell script
pip install pipenv
```

* Go to your desired development folder and create a new django project:

```shell
django-admin startproject django_ledger_project && cd django_ledger_project
```

* Install Django on you virtual environment.

```shell
pipenv install django
```

* Install Django Ledger

```shell script
pipenv install django-ledger[graphql,pdf]
```

* Activate your new virtual environment:

```shell
pipenv shell
```

* Add django_ledger to INSTALLED_APPS in you new Django Project.

```python
INSTALLED_APPS = [
    ...,
    'django_ledger',
    ...,
]
```

* Perform database migrations:

```shell
python manage.py migrate
```

* Add Django SuperUser and follow the prompts.

```shell
python manage.py createsuperuser
```

* Add URLs to your project's __urls.py__:

```python
from django.urls import include, path

urlpatterns = [
    ...,
    path('ledger/', include('django_ledger.urls', namespace='django_ledger')),
    ...,
]
```

* Run your project:

```shell
python manage.py runserver
```
