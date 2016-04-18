trailway
========

Dan learns programming by making things

Settings
--------

Moved to [settings].

Basic Commands
--------------

### Setting Up Your Users

To create a **normal user account**, just go to Sign Up and fill out the form. Once you submit it, you’ll see a “Verify Your E-mail Address” page. Go to your console to see a simulated email verification message. Copy the link into your browser. Now the user’s email should be verified and ready to go.

To create an **superuser account**, use this command:

    $ python manage.py createsuperuser

For convenience, you can keep your normal user logged in on Chrome and your superuser logged in on Firefox (or similar), so that you can see how the site behaves for both kinds of users.

### Test coverage

To run the tests, check your test coverage, and generate an HTML coverage report:

    $ coverage run manage.py test
    $ coverage html
    $ open htmlcov/index.html

#### Running tests with py.test

    $ py.test

### Live reloading and Sass CSS compilation

Moved to [Live reloading and SASS compilation].

### Celery

This app comes with Celery.

To run a celery worker:

``` sourceCode
cd trailway
celery -A trailway.taskapp worker -l info
```

Please note: For Celery’s import magic to work, it is important *where* the celery commands are run. If you are in the same folder with *manage.py*, you should be right.

### Email Server

In development, it is often nice to be able to see emails that are being sent from your application. If you choose to use [MailHog] when generating the project a local SMTP server with a web interface will be available.

To start the service, make sure you have nodejs installed, and then type the following:

    $ npm install
    $ grunt serve

(After the first run you only need to type `grunt serve`) This will start an email server that listens on `127.0.0.1:1025` in addition to starting your Django project and a watch task for live reload.

To view messages that are sent by your application, open your browser and go to `http://127.0.0.1:8025`

The email server will exit when you exit the Grunt task on the CLI with Ctrl+C.

It’s time to write the code!!!

Running end to end integration tests
------------------------------------

N.B. The integration tests will not run on Windows.

To install the test runner:

    $ pip install hitch

To run the tests, enter the trailway/tests directory and run the following commands:

    $ hitch init

Then run the stub test:

    $ hitch test stub.test

This will download and compile python, postgres and redis and

  [settings]: http://cookiecutter-django.readthedocs.org/en/latest/settings.html
  [Live reloading and SASS compilation]: http://cookiecutter-django.readthedocs.org/en/latest/live-reloading-and-sass-compilation.html
  [MailHog]: https://github.com/mailhog/MailHog
