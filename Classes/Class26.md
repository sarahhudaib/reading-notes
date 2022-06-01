# API Deployment

## How to install Heroku Command-Line on Ubuntu?

```
sudo curl https://cli-assets.heroku.com/install-ubuntu.sh | sh
```

If you get an error that says the `curl command is not found`, 
 install curl by executing:

```
sudo apt install curl
```
## How to deploy a Static Website using Heroku CLI on Ubuntu?
Once you have installed Heroku check on the version of Heroku
```
heroku -v
```

Run these commands
```
heroku apps:create <sarah-cookies-api> --> name of the app

# create the container 
heroku stack:set container 
```

> then the regular ACP 

```
git add .
git commit -am "something"
git push heroku main
```




if a problem is encountered about code not being pushed:

```
git init
heroku buildpacks:clear
heroku buildpacks:set heroku/python
heroku git:remote -a <app_name>
git add .
git commit -am "make it better"
git push heroku main
```

## Conclusion
It is easy to install Heroku CLI and configure it on Ubuntu. We can deploy a static website on Heroku by creating a python app. Similarly, we can also host python, nodejs, php, ruby… applications.
