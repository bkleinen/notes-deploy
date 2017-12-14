# This is a Demo App for Heroku Deployment of a Rails app via Travis
[![Build Status](https://travis-ci.org/bkleinen/notes-deploy.svg?branch=master)](https://travis-ci.org/bkleinen/notes-deploy)

## Plain Heroku Deployment

Requirements: install [Heroku CLI (command line interface)](https://devcenter.heroku.com/articles/heroku-cli)

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

## Heroku Deployment after an successfull travis build

To be able to deploy to your heroku account, travis needs your Heroku API key.
This can be done by adding it encrypted to the .travis.yml, which is automatically
done with

    gem install travis
    travis encrypt $(heroku auth:token) --add deploy.api_key

and further changes to .travis.yml as described in
[https://docs.travis-ci.com/user/deployment/heroku/](https://docs.travis-ci.com/user/deployment/heroku/)

The app deployed by heroku: [https://rocky-everglades-35483.herokuapp.com](https://rocky-everglades-35483.herokuapp.com)
