web: gunicorn config.wsgi:application
worker: celery worker --app=trailway.taskapp --loglevel=info
