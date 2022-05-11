# Django CRUD and Forms

## Django CRUD `(Create, Retrieve, Update, Delete)` Function Based Views

CRUD can be best explained as an approach to building a Django web application. In general CRUD means performing Create, Retrieve, Update and Delete operations on a table in a database.

- `Create` – create or add new entries in a table in the database. 
- `Retrieve` – read, retrieve, search, or view existing entries as a list(List View) or retrieve a particular entry in detail (Detail View) 
- `Update` – update or edit existing entries in a table in the database 
- `Delete` – delete, deactivate, or remove existing entries in a table in the database

--------

## Django Forms
When one creates a Form class, the most important part is defining the fields of the form. Each field has custom validation logic, along with a few other hooks. This article revolves around various fields one can use in a form along with various features and techniques concerned with Django Forms. 

`Forms` are basically used for taking input from the user in some manner and using that information for logical operations on databases. For example, Registering a user by taking input as his name, email, password, etc.

>> Django maps the fields defined in Django forms into HTML input fields. Django handles three distinct parts of the work involved in forms:

- preparing and restructuring data to make it ready for rendering
- creating HTML forms for the data
- receiving and processing submitted forms and data from the client

>>> Note that all types of work done by Django forms can be done with advanced HTML stuff, but Django makes it easier and efficient especially the validation part. Once you get hold of Django forms you will just forget about HTML forms.