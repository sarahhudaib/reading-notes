# JWT Authentication with Django REST Framework
`JSON Web Token` is an open standard for securely transferring data within parties using a JSON object. 

JWT is used for stateless authentication mechanisms for users and providers, this means maintaining session is on the client-side instead of storing sessions on the server. 

Here, we will implement the JWT authentication system in Django.

Modules required :
- django : Django Installation
- djangorestframework_simplejwt :

```
pip install djangorestframework_simplejwt
```

## Basic setup :

Start a project by the following command –

```
django-admin startproject config
```
Change directory to project config –

```
cd config
```
Start the server- Start the server by typing following command in terminal –

```
python manage.py runserver
```
To check whether the server is running or not go to a web browser and enter `http://127.0.0.1:8000/` as URL.

Now stop the server by pressing

```
ctrl-c
```

Let’s create an app now called the `“app”`.

```
python manage.py startapp app
```
adding configuration to settings.py file :

open `settings.py` file in config folder and add configuration.

```
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
}
```
edit `urls.py` file
open `urls.py` in config folder

```
from django.urls import path, include
from rest_framework_simplejwt import views as jwt_views
  
urlpatterns = [
    path('api/token/',
         jwt_views.TokenObtainPairView.as_view(),
         name ='token_obtain_pair'),
    path('api/token/refresh/',
         jwt_views.TokenRefreshView.as_view(),
         name ='token_refresh'),
    path('', include('app.urls')),
]
```

edit `views.py`
open `views.py` in app folder and make a API view

```
from rest_framework.views import APIView
from rest_framework.response import Response
from rest_framework.permissions import IsAuthenticated
  
  
class HelloView(APIView):
    permission_classes = (IsAuthenticated, )
  
    def get(self, request):
        content = {'message': 'Hello, GeeksforGeeks'}
        return Response(content)

```
edit `urls.py`
create a `urls.py` in app folder and edit it

```
from django.urls import path
from . import views
  
urlpatterns = [
    path('hello/', views.HelloView.as_view(), name ='hello'),
]
```
Usage :

To make an HTTP request we have used HTTPie, to install it.
```
$ sudo apt install httpie
```
---

### Step 1 :
migrate project, create a superuser and runserver

```
$ python manage.py migrate
$ python manage.py createsuperuser
$ python manage.py runserver 4000
```

### Step 2 :
Now, we need to authenticate and obtain the token. which we will get at endpoint is
`/api/token/`

```
$ http post http://127.0.0.1:4000/api/token username=spider password=vinayak
```
add your user name and password

### Step 3 :
copy access token and make a request

```
$  http http://127.0.0.1:4000/hello/ "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTg3Mjc5NDIxLCJqdGkiOiIzYWMwNDgzOTY3NjE0ZDgxYmFjMjBiMTBjMDlkMmYwOCIsInVzZXJfaWQiOjF9.qtNrUpyPQI8W2K2T22NhcgVZGFTyLN1UL7uqJ0KnF0Y" 
```

