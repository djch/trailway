web: waitress-serve --port=$PORT config.wsgi:application
worker: celery worker --app=trailway.taskapp --loglevel=info
