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

2. Create Project (PROJ_NAME = django_todo)
$ django-admin startproject PROJ_NAME .
    Note: Don’t forget the ‘.’ at the end of the command.

3. Create a new App (APP_NAME = *depends on the app e.g. todo)
$ python3 manage.py startapp APP_NAME

4. Install the Coverage tool 
$ pip3 install coverage

5. Install a database url package
$ pip3 install dj-database-url
    Note: This package allows us to parse the database url that Heroku created.

6.-Install Postgres
$ pip3 install psycopg2-binary
    Note: Postgres is a way for your content to ‘talk’ to the database on the back end

7. Install webserver
$ pip3 install gunicorn
    Note: Replaces the development server once the app is deployed to Heroku

8. Create superuser
$ python3 manage.py createsuperuser

9. To run the server
$ python3 manage.py runserver
    You will need to add the host name to ALLOWED_HOSTS.
    Run the server and start a browser and wait for the error which will contain the host name.
    
