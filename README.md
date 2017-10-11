# octobercms-heroku

```
composer create-project october/october myoctober
cd myoctober
php artisan october:env
```

Overwrite the config/app.php and config/cms.php from this repo, and copy Procfile into project root.

If you are not under version control already, create a local repo:
```
git init
```

Important: remove composer.lock from .gitignore!


Log into heroku and set up the cloud database:

```
heroku login
heroku create
heroku addons:create heroku-postgresql:hobby-dev
```

Push the codebase and create the db on remote side.

```
git add . --all
git commit -m "Heroku setup"
git push heroku master
heroku run bash

> php artisan october:up

```

Open heroku app, and move under /backend, login with admin/admin. It should work :)
