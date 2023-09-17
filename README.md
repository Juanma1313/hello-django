# Steps to create,run, test and deploy the Django app

It is possible to make a quick install of all required software using the following command:
$ pip install -r requirements.txt

But in following section we explain each commponent installation step by step 

## Setting up environment
1. Create file env.py
2. Add the env.py name to .gitignore file so it woll not export it to any external repository.
3. Add all new environmental variables needed that are not specific to the IDE to the env.py file
    # env.py
    import os
    os.environ["var_name"] = "var_value"

4. Add any environment variable for any specific environment following the service/framework/IDE config instructions.
   (e.g. for CodeAnywhere  use the dashboard to get to the settings/environment variables page.)


## Setting up Django 

1. Install Django
$ pip3 install 'django<4'
    Note: It's important to make sure that you download the official (and most supported) version of Django. As a result, you should download the latest version of 3. 

2. Create Project 
$ django-admin startproject PROJ_NAME .
    Note: Don’t forget the ‘.’ at the end of the command.

3. Create a new App
$ python3 manage.py startapp APP_NAME

4. To run the server
$ python3 manage.py runserver
    You will need to add the host name to ALLOWED_HOSTS. See this guide
