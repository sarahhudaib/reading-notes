# Introduction to Django

`Django` is a Web framework written in Python. A Web framework is software that supports the development of dynamic Web sites, applications, and services. It provides tools and functionalities that solve many common problems associated with Web development, such as security features, database access, sessions, template processing, URL routing, internationalization, localization, and much more.
Library: we built things from a specific library, ill choose the things.

`WRRC:` web request-response cycle

`APIs:` let your product or service communicate with other products and services without having to know how they’re implemented. This can simplify app development, saving time and money. When you’re designing new tools and products—or managing existing ones—APIs give you flexibility; simplify design, administration, and use; and provide opportunities for innovation.

## Why Django
A `“web framework”` is a collection of tools that abstract away much of the difficulty–and repetition–inherent in web development. For example, most websites need the same basic functionality: the ability to connect to a database, set URL routes, display content on a page, handle security properly, and so on. Rather than recreate all of this from scratch, programmers over the years have created web frameworks in all the major programming 

>> languages: `Django` in Python, `Rails` in Ruby, and `Laravel` in PHP among many, many others.


## Who’s Using Django?
It’s good to know who is using Django out there to have an idea of what you can do with it. Among the biggest Web sites using Django we have: are Instagram, Disqus, Mozilla, Bitbucket, and Last.FM, National Geographic.

## Starting a New Project:

-	To start a new Django project, run the command below:
```
django-admin startproject myproject
```
-	Now my project directory looks like this:

 

## Our initial project structure is composed of five files:

•	`manage.py`: a shortcut to use the Django-admin command-line utility. It’s used to run management commands related to our project. We will use it to run the development server, run tests, create migrations, and much more.
•	`__init__.py`: this empty file tells Python that this folder is a Python package.
•	`settings.py`: this file contains all the project’s configurations. We will refer to this file all the time!
•	`urls.py`: this file is responsible for mapping the routes and paths in our project. For example, if you want to show something in the URL /about/, you have to map it here first.
•	`wsgi.py`: this file is a simple gateway interface used for deployment. You don’t have to bother about it. Just let it be for now.

`Django` comes with a simple web server installed. It’s very convenient during the development, so we don’t have to install anything else to run the project locally. We can test it by executing the command:

        python manage.py run server
 



## Django Apps
In the Django philosophy we have two important concepts:
- `App`: is a Web application that does something. An app usually is composed of a set of models (database tables), views, templates, and tests.
- `Project`: is a collection of configurations and apps. One project can be composed of multiple apps or a single app.

>> `OSS` (open-source software)
https://opensource.com/resources/what-open-source 

## MVC Pattern and Django
1.	Web browser or client sends the request to the web server, asking the server to display a blog post.
2.	The request received by the server is passed to the controller of the application.
3.	The controller asks the model to fetch the blog post.
4.	The model sends the blog post to the controller.
5.	The controller then passes the blog post data to the view.
6.	The view uses blog post data to create an HTML page.
7.	At last, the controller returns the HTML content to the client.

 
## MTV (Model-Template-View)
 
Internationalization, localization
-	Internationalization
Preparing the software for localization. Usually done by developers.
-	Localization
Writing the translations and local formats. Usually done by translators.


## Steps for creating a Django project
-	poetry new example-lab
-	cd example-lab
-	poetry install
-	poetry shell
-	poetry add django
-	cd example-lab
-	rm –r test django-things
-	django-admin startproject myproject
-	cd myproject
-	code .
-	python .\manage.py migrate // when we create the project // 2.Whenever we create a new model  
-	python manage.py createsuperuser
-	python manage.py runserver
-	python manage.py startapp my_app
