## Shopping List
App created with MERN stack.

Following Traversy Media tut.

Master branch is ready to be deployed to heroku app.

## Prerequisites
- [Account on Heroku](https://heroku.com)
- [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli) installed
- [MongoDB Account](https://cloud.mongodb.com/user#/atlas/login) or another mongodb service

## How to deploy - Step-by-step
If you came accross some error create an issue :)

#### MongoDB

Firstly you need a Mongo database. 

I would suggest creating a cluster at mongodb.com since I am also using this service.

After creating account and/or cluster click on `connect` then click on `Connect Your Application` and select `Node.js` as driver (version 3.0 or later). 

Then copy the `Connection String Only`. This will be your value for DB key on Heroku app -explained below.

For [example](https://docs.atlas.mongodb.com/driver-connection/#connect-your-application)
Key: DB
Value: `mongodb+srv://<user>:<password>@cluster0.mongodb.net/<nameofdatabase>?ssl=true&authSource=admin`

If you are asked to type in a name of collection during creation of database, type in whatever you want ~~`shopping-list`. There is a bug if you do not type this. This bug is fixed in develop branch and will be merged into master in later commits.~~ 

Bug was fixed :blush:

#### Heroku
Open terminal
- `heroku login` -  login to your heroku account
- `heroku create` - this will create an app of some sort on your heroku acc.
 

Go to your `appname`, then settings.
Click on `Reveal Config Vars` and add following keys:
- DB: Value is your mongodb connections string, which you got above
Value should look like this
`mongodb+srv://<user>:<password>@cluster0.mongodb.net/<nameofdatabase>?ssl=true&authSource=admin`
- JWT: Value "sl_myJwtSecret"

This should be all. If anything occurs create an issue.

#### Deployment

In terminal type these commands (in order shown below)
- `git clone` this repo
- `cd` into the cloned repo

- `heroku git:remote <name of the created heroku app>`
- `git push heroku master` - push into the heroku repo

This will build an app on your acc.

  
While in your heroku app dashboard click on `Open app`. 

Done! Now go! Prepare your shopping list for your next trip to the mall :blush:
