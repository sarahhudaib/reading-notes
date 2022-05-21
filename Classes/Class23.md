# Django REST Framework & Docker

Django projects not only depend on Python requirements but also many system requirements, such as a web server, database, operating system, etc. When developing a Django project, you need to ensure that all environments and all developers will have all the same requirements installed. One way to keep those dependencies in sync is to use Docker. With Docker, we can have different versions of the database, web, or other servers required individually for each project. 

## What you’ll learn:

- How to set up Django Rest Framework with Docker and GitHub.
- How to use docker and docker-compose.
- Create a project and set your app running.
- Basic git commands.

## How to set up Django Rest Framework with Docker and GitHub

- Set up a new GitHub Project
- Add Requirements file (`requirements.txt`)
- Create a Dockerfile
    - Install Docker
- A Dockerfile is simply a file that contains a list of instructions or dependencies for Docker to build a docker image. Now let's create our Dockerfile. Simply create a new file at the root of our project called "Dockerfile". The file needs to begin with capital D and doesn't have any extension at the end.

- The first line of the Dockerfile is the image, that you are going to inherit from your Dockerfile. So basically with Docker, you can build images on top of other images.

- We are going to create our Dockerfile with Python 3.7 image. You can visit https://hub.docker.com to find a list of available images, the one we are going to use is alpine3.7

- Create an empty folder called app, because this will be required by our Dockerfile, and enter the commands as shown below.

## Docker commands:
- `FROM python:3.6-alpine` - This is the Python image that we are going to inherit from our Dockerfile. Alpine image is a very lightweight and minimal image that runs Python.
- `MAINTAINER Pradeep` - This is optional, but it is used to know who is maintaining the project.
- `ENV PYTHONUNBUFFERED 1` - This is recommended when running Python in docker containers. The reason for this is that it doesn't allow python to buffer the outputs. It just prints them directly, and this avoids any complications when running Python applications.
- `COPY ./requirements.txt /requirements.txt` - Copy our local requirements JSON, to our docker image.
- `RUN pip install -r /requirements.txt` - This will install our requirements from a .txt file using PIP.
- `RUN mkdir /app` - This creates an empty directory within our docker image to store our application's source code.
- `WORKDIR /app` - Switches to the default directory, unless we specify otherwise.
- `COPY ./app /app` - Copy the app folder from our local machine to our image, which consists of our project code.
- `RUN adduser -D user` - This will create a user that's gonna run our application on Docker. For security purposes, if we don't do this, then the image will run our application with a root account. If somebody compromises our application, they can get root access, which is very dangerous.
- `USER user` - Switch to that user.

---
## Docker Compose Configuration
Docker-compose is a tool that allows us to run our docker images and manage services configuration (e.g. Postgres Service, Redis Service) for our project.

- Create a new file named "`docker-compose.yml`" on the root of your project and enter the commands as shown below. This is a .yml file that contains the configuration of all the services that make up our project.

- version: "3" - Version of the docker compose.
- services: - Services that make up our project. Right now we only need one service for our python Django application.

    - app: - Service called app

        - build: - Build section of the configuration.
            - context: . - We are sending context to "." which is our current directory.
        - ports:
            -"8000:8000" - Map our project on port 8000 on our host to 8000 on the image.
        - volumes: - Whenever you change something in your project, it automatically updates changes in the container in Real-Time, so you don't need to restart the containers to reflect the changes.
            - ./app/app - Maps app directory of our project to app the directory in our docker image.
        - command: > - Command that is used to run our application on our docker container.

            - sh -c "python manage.py runserver 0.0.0.0:8000" 
            - shell command to run our application. This will start our development server on port 8000, available on all IP Address's that run on the container.
            
---
## Build Your Project:
in the terminal
```
docker-compose build
```
## Creating Django Project:
in the terminal
```
docker-compose run app sh -c "django-admin.py startproject app ."
```
## settings.py
```
 INSTALLED_APPS = [
     'django.contrib.admin',
     'django.contrib.auth',
     'django.contrib.contenttypes',
     'django.contrib.sessions',
     'django.contrib.messages',
     'django.contrib.staticfiles',
     'myapp',
 ]
```

## Now that we have created our Django project, We can verify by running
```
docker-compose run app sh -c "python manage.py runserver"
```

## Now that our setup is successful, We can go ahead and commit that to git

```
 pradeep@Latitude-5590:~/Desktop/DRF/DRF-Guide$ git add .
pradeep@Latitude-5590:~/Desktop/DRF/DRF-Guide$ git commit -am 'Setup Docker and Django Project'
[main 3f9bac5] Setup Docker and Django Project
8 files changed, 200 insertions(+)
create mode 100644 Dockerfile
create mode 100644 app/app/__init__.py
create mode 100644 app/app/settings.py
create mode 100644 app/app/urls.py
create mode 100644 app/app/wsgi.py
create mode 100755 app/manage.py
create mode 100644 docker-compose.yml
create mode 100644 requirements.txt
pradeep@Latitude-5590:~/Desktop/DRF/DRF-Guide$ git push origin main
Counting objects: 12, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (11/11), done.
Writing objects: 100% (12/12), 3.12 KiB | 1.04 MiB/s, done.
Total 12 (delta 0), reused 0 (delta 0)
ceaa4f6..3f9bac5  main -> main
```
