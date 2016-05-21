web: waitress-serve --port=80 config.wsgi:application
worker: celery worker --app=trailway.taskapp --loglevel=info
