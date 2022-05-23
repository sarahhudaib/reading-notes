# Permissions & Postgresql

## **`Permissions in Django REST Framework`**
In DRF, permissions, along with authentication and throttling, are used to grant or deny access for different classes of users to different parts of an API.

> Authentication and authorization work hand in hand. Authentication is always executed before authorization.

While authentication is the process of checking a user's identity (the user the request came from, the token that it was signed with), authorization is a process of checking if the request user has the necessary permissions for executing the request (are they a super user, are they the creators of the object).

>The authorization process in DRF is covered by permissions.

### **View Permissions**
APIView has two methods that check for permissions:

- check_permissions checks if the request should be permitted based on request data
- check_object_permissions checks if the request should be permitted based on the combination of the request and object data

### **Permission classes**

Permissions in DRF are defined as a list of permission classes. You can either create your own or use one of the seven built-in classes. All permission classes, either custom or built-in, extend from the BasePermission class:
```
class BasePermission(metaclass=BasePermissionMetaclass):

    def has_permission(self, request, view):
        return True

    def has_object_permission(self, request, view, obj):
        return True
```
As you can see, BasePermission has two methods, `has_permission` and `has_object_permission`, that both return True. 

> The permission classes override one or both of the methods to conditionally return True.

Turn back to the check_permissions and check_object_permissions methods from the beginning of the article:

- heck_permissions calls has_permission for each of the permissions
- check_object_permissions calls has_object_permission for each of the permissions as well

### **has_permission**
`has_permission` is used to decide whether a request and a user are allowed to access a specific view

For example:

- Is the request method allowed?
- Is the user authenticated?
- Is the user an admin or super user?

> has_permission possesses knowledge about the request, but not about the object of the request.

As explained at the beginning, has_permission (called by check_permissions) gets executed before the view handler is executed, without explicitly calling it.

### **has_object_permission**
has_object_permission is used to decide whether a specific user is allowed to interact with a specific object

For example:

- Who created the object?
- When was it created?
- In which group does the object belong to?

Besides the knowledge of the request, has_object_permission also possesses data about the object of the request. The method executes after the object is retrieved from the database.

> Unlike has_permission, has_object_permission isn't always executed by default:

- With an `APIView`, you must explicitly call `check_object_permission` to execute `has_object_permission` for all permission classes.
- With `ViewSets` (like `ModelViewSet`) or Generic Views (like `RetrieveAPIView`), `has_object_permission` is executed via `check_object_permission` inside a `get_object` method out of the box.
- `has_object_permission` is never executed for list views (regardless of the view you're extending from) or when the request method is `POST` (since the object doesn't exist yet).
- When any `has_permission` returns `False`, the `has_object_permission` doesn't get checked. The request is immediately rejected.

---

## **`Postgresql`**

### What is PostgreSQL?
PostgreSQL is a free and open-source relational database system. It provides the developer with extensibility and scalability. It works with a lot of programming languages and all major operating systems such as Windows, macOS, and Linux. 

### Installing PostgreSQL

- You can install PostgreSQL with the following command in the terminal.
```
sudo apt-get update
sudo apt-get install python-pip python-dev libpq-dev postgresql postgresql-contrib
```

- Now, you may start up postresql after its installation with the following command.
```
brew services start postgresql
```
### Creating a Database
- create our database and new user
```
sudo su - postgres
```
- interactive database 
```
psql
```
- Now, we shall create a database for this project.
```
CREATE DATABASE mydb;
```
### Creating a Database User
- create a database user for our database.
```
CREATE USER myuser WITH PASSWORD 'password';
```
- grant access rights to our new user to enable it to work on the database.
```
GRANT ALL PRIVILEGES ON DATABASE mydb TO myuser;
```
- exit the current user's shell session and get back to the postgres user's session
```
\q
```
- leave the postgreSQL and back to the terminal
```
exit
```
### Setting up Django Database Configuration

Inside the settings.py file of the project, you will see the DATABASES section. It looks like the following:
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}
```

We need to change the SQLite database configuration to the PostgreSQL database that we created.

```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql_psycopg2',
        'NAME': 'myproject',
        'USER': 'myuser',
        'PASSWORD': 'password',
        'HOST': 'localhost',
        'PORT': '',
    }
}
```