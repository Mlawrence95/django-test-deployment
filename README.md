# Deploying Sites

Options include `elastic beanstalk`, `heroku`, `python anywhere`,
`digital ocean`, and more.

Here's an attempt at using Heroku:
1. `brew install heroku/brew/heroku`
2. `heroku login`
3. `heroku create` in project directory
4. Make sure `STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')` is in `settings.py`
5. Create `Procfile`. This will look like `web: python manage.py runserver`
6. commit + push all changes, then `git push heroku master`
7. Create an instance of this app with `heroku ps:scale web=1`

### Setting up GitHub
First, make a dedicated repository for the deployment.
