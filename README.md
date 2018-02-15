# CollectablePengiunsApp

## Setup

Start up a fabric and deploy the collectable-penguin-network

## Running the app

Run `npm start` to run the app. This will start the app on http://localhost:4200/

## Starting the rest server

The app requires two rest servers to be running. 

Run the following to setup the required environment variable. Replace <CLIENT_ID> and <CLIENT_SECRET> variables

```
  export COMPOSER_PROVIDERS='{
    "github": {
      "provider": "github",
      "module": "passport-github",
      "clientID": "<CLIENT_ID>",
      "clientSecret": "<CLIENT_SECRET>",
      "authPath": "/auth/github",
      "callbackURL": "/auth/github/callback",
      "successRedirect": "http://localhost:4200?loggedIn=true",
      "failureRedirect": "/"
    }
  }'
```

Run `composer-rest-server -c admin@collectable-penguin-network -m true` to start the multi-user rest server

Run `composer-rest-server -c admin@collectable-penguin-network -p 3001` to start the rest server that will create identities
