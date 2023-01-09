# Why Virtualenv is Important for Django Development

## Create a separate virtual environment for each project:
`Virtualenv` is a tool that allows you to create a separate Python environment for each `Django` project you work on. This can be particularly useful if you need to work with different versions of `Django` and/or different libraries and packages for different projects.

## Example: 
For example, imagine that you are working on two Django projects, `Project A` and `Project B`. 

`Project A` requires **Django 2.2** and a specific version of the library X, while `Project B` requires **Django 3.1** and a different version of library X. Without using virtualenv, you would need to install both **Django 2.2** and **Django 3.1**, as well as the two different versions of library X on your system. This could lead to conflicts between the different versions of Django and library X, which could make it difficult or impossible to run one or both of the projects.

However, if you use virtualenv, you can create a separate virtual environment for each project, with its own copy of Django and the required libraries. This way, you can have **Django 2.2** and the specific version of library X installed in the virtual environment for `Project A`, and **Django 3.1** and the other version of library X installed in the virtual environment for `Project B`. This allows you to run both projects concurrently without any conflicts.

## Install and manage packages and libraries:
In addition to helping you manage dependencies, virtualenv also makes it easier to install and manage the packages and libraries that your project depends on. You can use tools like pip to install and update these dependencies within the virtual environment, without affecting the packages and libraries installed on your system.

## Steps to create a virtual environment with Python:
1. Install virtualenv:
    ```
    pip install virtualenv
    ```
2. Create a virtual environment with Python 3.6:
    ```
    virtualenv -p python3.6 myenv
    ```
> This will create a new directory called "myenv" that contains the Python 3.6 interpreter and other files needed for the virtual environment.

3. Activate the virtual environment:
    ```
    source myenv/bin/activate
    ```
> This will activate the virtual environment, and you should see the name of the virtual environment in the command prompt, like this:

```
(myenv)$
```

4. Install the packages you need for your project:
    ```
    pip install django
    ```

> You can install multiple packages by separating them with spaces, like this:

```
pip install django requests
```
5. Freeze the installed packages:
```
pip freeze > requirements.txt
```

> This will create a file called "requirements.txt" that lists all the packages and their versions that are installed in the virtual environment. You can use this file to install the same packages in a different environment or on a different machine.

To install the packages from the requirements file, use the following command:

```
pip install -r requirements.txt
```


## Sum it up!
Overall, virtualenv is a valuable tool for Django developers, as it allows you to easily manage dependencies and avoid conflicts between different versions of libraries and packages. By using virtualenv, you can ensure that your Django projects are isolated and easy to maintain.

- It allows you to isolate the dependencies for different Django projects, so that you can have different versions of libraries and packages installed for each project.
- It makes it easier to manage the packages and libraries that your project depends on, as you can use tools like pip to install and manage these dependencies within the virtual environment.
- It can help you avoid conflicts between different versions of libraries and packages that may be required by different projects.