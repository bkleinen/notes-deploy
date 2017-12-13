# This is a Demo App for Heroku Deployment of a Rails app via Travis

## Plain Heroku Deployment

### First step: start with heroku deployment from command line

Followed the guide at:
https://devcenter.heroku.com/articles/getting-started-with-rails5

At the very least it is necessary to add the pg gem only to production group,
and adapt config/database.yml to use pg in production. Then run:

    heroku login
    heroku create
    git push heroku master
    heroku run rails db:migrate
    heroku open

The name of my app is [secret-basin-23674](https://secret-basin-23674.herokuapp.com/).
