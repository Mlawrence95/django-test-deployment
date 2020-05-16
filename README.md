# Deploying Sites

Options include `elastic beanstalk`, `heroku`, `python anywhere`,
`digital ocean`, and more.

NOTE: the following exposes keys to public. This is not acceptable for anything that isn't a toy.


Here's an attempt at using Heroku:
- Create an account for [heroku](https://dashboard.heroku.com)
- `brew install heroku/brew/heroku`
- `heroku login`
- `heroku create` in project directory
- Make sure `STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')` is in `settings.py`
- Create `Procfile`. This will look like `web: gunicorn boilerplate_django.wsgi --log-file -`
- get heroku server name and add it to `settings.py` like
`ALLOWED_HOSTS = ["obscure-everglades-57275.herokuapp.com"]`
- commit + push all changes, then `git push heroku master`
- Verify locally. `python manage.py collectstatic; heroku local`.
- Create an instance of this app with `heroku ps:scale web=1`
- access with `heroku open`
- view `heroku logs --tail` as needed
- run commands like `heroku run python manage.py createsuperuser`


CSS will be broken for `admin`, as well as anything
that depends on `static/`. Not sure how to resolve for now.
