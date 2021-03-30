# Reminders

## Create heroku app for production
``` bash
heroku create dmg-wordcount-pro
```
douglasmg7@lyptus:~/code/flask-by-example$ heroku create dmg-wordcount-pro
Creating ⬢ dmg-wordcount-pro... done
https://dmg-wordcount-pro.herokuapp.com/ | https://git.heroku.com/dmg-wordcount-pro.git

## Create heroku app for stage
``` bash
heroku create dmg-wordcount-stage
```
douglasmg7@lyptus:~/code/flask-by-example$ heroku create dmg-wordcount-stage
Creating ⬢ dmg-wordcount-stage... done
https://dmg-wordcount-stage.herokuapp.com/ | https://git.heroku.com/dmg-wordcount-stage.git

## Add remote heroku for stage and production
``` bash
git remote add pro https://git.heroku.com/dmg-wordcount-pro.git
git remote add stage https://git.heroku.com/dmg-wordcount-stage.git
```

### Not working for git@heroku.com
``` bash
git remote add pro git@heroku.com:dmg-wordcount-pro.git
git remote add stage git@heroku.com:dmg-wordcount-stage.git
```

## For push heroku stage and production
``` bash
git push stage main
git push pro main
```

## Set env vars
``` bash
heroku config:set APP_SETTINGS=config.StagingConfig --remote stage
heroku config:set APP_SETTINGS=config.ProductionConfig --remote pro
``` 

## Run app
``` bash
heroku run python app.py --app dmg-wordcount-stage
heroku run python app.py --app dmg-wordcount-pro
```

## Initialize Alembic:
``` bash
cd ~/code/flask-by-example
python manage.py db init
```

## Create first migration:
``` bash
cd ~/code/flask-by-example
python manage.py db migrate
```

## Apply the upgrades to the database:
``` bash
cd ~/code/flask-by-example
python manage.py db upgrade
```

## Check if we have a database set up no the staging server:
``` bash
heroku config --app wordcount-stage
```

## Add the postgres addon to the staging server:
``` bash
heroku addons:create heroku-postgresql:hobby-dev --app dmg-wordcount-stage
```
### To view documentation
``` bash
heroku addons:docs heroku-postgresql
```
