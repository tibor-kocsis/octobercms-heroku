# Running OctoberCMS on Heroku with Heroku PostgreSQL

Start from stratch, create a brand new OctoberCMS:

```
composer create-project october/october myoctober
```

Change the config the external environment:

```
php artisan october:env
```

Overwrite the config/app.php and config/cms.php from this repo, and copy Procfile into project root.

If you are not under version control already, create a local repo:
```
git init
```

Important: remove composer.lock from .gitignore!


Log in to heroku and set up the cloud database:

```
heroku create
heroku addons:create heroku-postgresql:hobby-dev
```

Push the codebase:

```
git add . --all
git commit -m "Heroku setup"
git push heroku master
```

Log in to the app with an on-off dyno, and run the db migrations

```
heroku run bash

> php artisan october:up
```

Open heroku app and login with admin/admin under /backend url. It should work :)
