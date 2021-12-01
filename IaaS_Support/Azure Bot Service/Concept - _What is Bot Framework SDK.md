# _What is Bot Framework SDK
   

Bot Framework provides the most comprehensive experience for building conversation applications. The service defines a REST API and an activity protocol for how your bot and channels or users can interact, so that you can focus on the conversational logic.

## Bot Class
The SDK defines a bot class that handles the conversational reasoning for the bot app. The bot class:

-   Recognizes and interprets the user's input.
-   Reasons about the input and performs relevant tasks.
-   Generates responses about what the bot is doing or has done.

![[Pasted image 20210713163830.png]]


What's more with the [Bot Framework SDK](https://github.com/microsoft/botframework-sdk#bot-framework-sdk-v4), developers can build bots that converse free-form or with guided interactions including using simple text or rich cards that contain text, images, and action buttons.

The latest version, Bot Framework SDK v4, is an [open source SDK](https://github.com/microsoft/botframework-sdk/#readme) that enable developers to model and build sophisticated conversation using their favorite programming language.

Supported language: C#, JS, Python, Java

## Adapter Class
The SDK defines an adapter class that handles connectivity with the channels.

The adapter:

-   Provides a method for handling requests from and methods for generating requests to the user's channel.
-   Includes a middleware pipeline, which includes turn processing outside of your bot's turn handler.
-   Calls the bot's turn handler and catches errors not otherwise handled in the turn handler.

In addition, bots often need to retrieve and store state each turn. This is handled through storage, bot state, and property accessor classes. The SDK does not provide built-in storage, but does provide abstractions for storage and a few implementations of a storage layer.

![[Pasted image 20210713164026.png]]


### Note 

The bot has 15 seconds to acknowledge the call with a status 200 on most channels. If the bot does not respond within 15 seconds, an HTTP GatewayTimeout error (504) occurs.

[GitHub - microsoft/botframework-sdk: Bot Framework provides the most comprehensive experience for building conversation applications.](https://github.com/microsoft/botframework-sdk)