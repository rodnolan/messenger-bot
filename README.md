# Masterclass for Developers Messenger Platform Sample Bot 

This project is an example server built in Node. It is used in the Masterclass for Developers training curriculum and is based on the project originally posted [here](https://github.com/fbsamples/messenger-platform-samples). 

This version contains the following functionality:
* Webhook (specifically for Messenger Platform events)
* Send API 
* Messenger Platform v1.1 features

You can learn more about the Messenger Platform [here](https://developers.facebook.com/docs/messenger-platform/quickstart).

## Getting Started

Get the code
```cmd
git clone git@github.com:rodnolan/messenger-bot.git
```

Study the commit history
```cmd
git log --oneline
```

Checkout a version of the code that represents a basic starting point   
```cmd
git checkout <commit hash of the 'first commit'>
```

Store that code in a branch so you can track your progress as you work through the lab exercises
```cmd
git checkout -b <branch-name-holding-your-version-of-the-project>
```

At any time you can refer to the completed version of the application. 
```cmd
git log --oneline
git checkout <commit hash of the final commit>
```

If you prefer to work without git you can use these files:

the starter version of the project is here: 
https://rodnolan.github.io/posterific-static-images/bot-base.zip

the completed version of the bot application is here: 
https://rodnolan.github.io/posterific-static-images/bot-final.zip

## Setup and start your server

Before starting the server, you must do some basic setup to prepare your server to run. 

1) install all dependencies
```cmd
npm install
```
or
```cmd
yarn install
```
2) start your local server
```cmd
npm start
```

## Customize application settings to match your Facebook application

These steps are covered in more detail in the course manual but here's the quick reference:

1) edit the variables defined in `config/default.json` to match those associated with your own Facebook application. Descriptions of each parameter can be found in `app.js`.
2) restart your node server so that the latest values are read from `config/default.json`
3) start [ngrok](https://ngrok.com/) to expose your local server to the Messenger Platform 
```cmd
ngrok http 5000
```
    This tool will allow you to run your server locally while enjoying the ability to develop and debug the code in your IDE. Don't forget to restart your node server every time you make changes to your code.

4) Configure your Facebook application's webhook subscription to connect to your bot server via your ngrok tunnel: `https://abcd1234.ngrok.io/webhook`.

5) Send a message to your bot using the Send Message button on your Facebook Page and ensure that the message is received by your bot.

    Use the ngrok Web Interface http://127.0.0.1:4040 to view requests to your ngrok url

## Learn more about the Messenger Platform

All webhook code is in `app.js`. All requests from the Messenger Platform are routed to `/webhook`. This project handles callbacks for authentication, messages, delivery confirmation and postbacks. More details are available at the [reference docs](https://developers.facebook.com/docs/messenger-platform/webhook-reference).
