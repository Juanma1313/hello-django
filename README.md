# Steps to create,run, test and deploy the Django app

It is possible to make a quick install of all required software using the following command:
$ pip install -r requirements.txt

But in following section we explain each commponent installation step by step 

## Setting up environment
1. Create file env.py
2. Add the env.py name to .gitignore file so it will not export it to any external repository.
3. Add all new environmental variables needed that are not specific to the IDE to the env.py file

    `import os`
    `os.environ["SECRET_KEY"] = "ayuz2!a(25(j!ks % p= & _70ip0*378xfaq5z & hiwpzwkfr8-3)x"`
    `os.environ["DEVELOPMENT"] = "True"`
    `os.environ["ALLOWED_HOSTS"] = "8000-juanma1313-hello-django-7prqkf04og.us2.codeanyapp.com"`
    `os.environ["var_name"] = "var_value"`

    >[!NOTE]
    In case the IDE does not permiate its defined environment variable, this can be also a place to put them
    Just remembet to do step 2 and/or change its content in the external/production environment

4. Add any environment variable for any specific environment following the service/framework/IDE config instructions.
   (e.g. for CodeAnywhere  use the dashboard to get to the settings/environment variables page.)
   
   > [!NOTE]
   This step can be ignored if all variables are defined in env.py


## Setting up Django 

1. Install Django

    `$ pip3 install 'django<4'`

    >It's important to make sure that you download the official (and most supported) version of Django.
    As a result, you should download the latest version of 3. 

2. Create Project (PROJ_NAME = django_todo)

    `$ django-admin startproject PROJ_NAME .`

    >Don't forget the '.' at the end of the command.

3. Create a new App 

    `$ python3 manage.py startapp APP_NAME`

     >APP_NAME = *depends on the app e.g. todo

4. Install the Coverage tool

    `$ pip3 install coverage`

5. Install a database url package

   `$ pip3 install dj-database-url`

    >This package allows us to parse the database url that Heroku created.

6. Install Postgres

    `$ pip3 install psycopg2-binary`

    >Postgres is a way for your content to ‘talk’ to the database on the back end

7. Install webserver

    `$ pip3 install gunicorn`

    >Replaces the development server once the app is deployed to Heroku

8. Migrate database (setup database and create tables )

    `$ python3 manage.py makemigrations --dry-run`

    >Runs a test migration run. 

    `$ python3 manage.py showmigrations`

    >Show migrations, Optional 

    `$ python3 manage.py makemigrations`

    >Make migrations script

    `$ python3 manage.py migrate --plan`

    >cCheck Migration plan,  Optional 

    `$ python3 manage.py migrate`

    >Execute migration plan

9. Create superuser

    `$ python3 manage.py createsuperuser`

10. To run the server

    `$ python3 manage.py runserver`

    >You will need to add the host name to ALLOWED_HOSTS. Run the server and start a browser and wait for the error which will contain the host name.
