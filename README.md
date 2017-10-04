# Masterclass for Developers Messenger Platform Sample Bot 

This project is an example server built in Node. It is used in the Masterclass for Developers training curriculum and is based on the project originally posted [here](https://github.com/fbsamples/messenger-platform-samples). 

This version contains the following functionality:
* Webhook (specifically for Messenger Platform events)
* Send API 
* Messenger Platform v1.1 features

You can learn more about the Messenger Platform [here](https://developers.facebook.com/docs/messenger-platform/quickstart).

## Setup

Set the values in `config/default.json` before running the sample. Descriptions of each parameter can be found in `app.js`.

## Run

You can start the server on your local machine by running `npm start`. However, the webhook must be at a public URL that the Messenger Platform servers can reach. Therefore, a tunnelling tool such as [ngrok](https://ngrok.com/) is required to  temporarily and securely expose your localhost server. This tool will allow you to run your server locally while enjoying the ability to develop and debug the code in your IDE. 

## Webhook

All webhook code is in `app.js`. It is routed to `/webhook`. This project handles callbacks for authentication, messages, delivery confirmation and postbacks. More details are available at the [reference docs](https://developers.facebook.com/docs/messenger-platform/webhook-reference).
