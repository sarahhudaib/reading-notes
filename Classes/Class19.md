# Django Models

A `Django model` is the built-in feature that Django uses to create tables, their fields, and various constraints. 

>> In short, `Django Models` is the SQL of Database one uses with Django. 

`SQL` (Structured Query Language) is complex and involves a lot of different queries for creating, deleting, updating or any other stuff related to database. Django models simplify the tasks and organize tables into models. Generally, each model maps to a single database table. 


## How one can use Django models to store data in the database conveniently?
 Moreover, we can use admin panel of Django to create, update, delete or retrieve fields of a model and various similar operations. 
 
 Django models provide simplicity, consistency, version control and advanced metadata handling. 

 ## Basics of a model include

 - Each model is a Python class that subclasses `django.db.models.Model`.
- Each attribute of the model represents a database field.
- With all of this, Django gives you an automatically-generated database-access API.

## Using Django Models
- To use Django Models, one needs to have a project and an app working in it. 
- After you start an app you can create models in app/models.py.

## Creating a Model

``` python
from django.db import models
        
class ModelName(models.Model):
        field_name = models.Field(**options)
```

Whenever we create a Model, Delete a Model, or update anything in any of `models.py` of our project. We need to run two commands `makemigrations` and `migrate`. 

>> makemigrations basically generates the SQL commands for preinstalled apps (which can be viewed in installed apps in settings.py) and your newly created app’s model which you add in installed apps whereas migrate executes those SQL commands in the database file. 

```
Python manage.py makemigrations
```

## Render a model in Django Admin Interface
To render a model in Django admin, we need to modify app/admin.py. Go to admin.py in geeks app and enter the following code. Import the corresponding model from models.py and register it to the admin interface.


``` python
from django.contrib import admin

# Register your models here.
from .models import GeeksModel

admin.site.register(GeeksModel)
```

## Django CRUD – Inserting, Updating and Deleting Data

`Django` lets us interact with its database models, i.e. add, delete, modify and query objects, using a database-abstraction API called 
> ORM(Object Relational Mapper). 

We can access the Django ORM by running the following command inside our project directory.
 
```
python manage.py shell
```
