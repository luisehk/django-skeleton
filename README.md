# django-skeleton
This is the base code I use for all my Django projects.

### Installation
To install the Python and [Bower](http://bower.io/) dependencies just run:

    make install

### Running the app
The app consists on multiple processes: gunicorn to run the Django app, the simple http server for the web front-end and celery for the message queue. To run them on the same time I use [Foreman](https://github.com/ddollar/foreman) (you will need Ruby for that):

    gem install foreman

If you want to override some setting from your settings.py file, Foreman will read the .env fileon your root directory and send them to Django as environmental variables. For example:

    DATABASE_URL=sqlite:/db.sqlite3
	SECRET_KEY=i5o@y&|@2!"·&|(g3tb5u#c^3@(tz6^pci=e
	TIME_ZONE=America/Monterrey

If you don't want to use Foreman, you can run the processes found on the Procfile manually. Make sure you configure your app through environmental variables with the following command:

    export DATABASE_URL=sqlite:/db.sqlite3

Now, start the app:

    make run

For first time use, you need to run the Django migrations:

    make migrate

### Unit testing
Just run the following command:

    make test

