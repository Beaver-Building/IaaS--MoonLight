# _What is Bot
   

Bots provide an experience that feels less like using a computer and more like dealing with a person - or at least an intelligent robot. They can be used to shift simple, repetitive tasks, such as taking a dinner reservation or gathering profile information, on to automated systems that may no longer require direct human intervention. Users converse with a bot using text, interactive cards, and speech. A bot interaction can be a quick question and answer, or it can be a sophisticated conversation that intelligently provides access to services.

A bot can be thought of as a web application that has a conversational interface. A user connects to a bot though a channel such as Facebook, Slack, or Microsoft Teams.

-   The bot reasons about input and performs relevant tasks. This can include asking the user for additional information or accessing services on behalf of the user.
-   The bot performs recognition on the user's input to interpret what the user is asking for or saying.
-   The bot generates responses to send to the user to communicate what the bot is doing or has done.
-   Depending on how the bot is configured and how it is registered with the channel, users can interact with the bot through text or speech, and the conversation might include images and video.

![[Pasted image 20210713162935.png]]

Bots are a lot like modern web applications, living on the internet and using APIs to send and receive messages. What's in a bot varies widely depending on what kind of bot it is. Modern bot software relies on a stack of technology and tools to deliver increasingly complex experiences on a wide variety of platforms. However, a simple bot could just receive a message and echo it back to the user with very little code involved.

Bots can do the same things other types of software can do - read and write files, use databases and APIs, and do the regular computational tasks. What makes bots unique is their use of mechanisms generally reserved for human-to-human communication.

The Azure Bot Service and the Bot Framework offer:

-   The Bot Framework SDK for developing bots
-   Bot Framework Tools to cover end-to-end bot development workflow
-   Bot Framework Service (BFS) to send and receive messages and events between bots and channels
-   Bot deployment and channel configuration in Azure

Additionally, bots may use other Azure services, such as:

-   Azure Cognitive Services to build intelligent applications
-   Azure Storage for cloud storage solution


## Summary
### Client / Channel
	Authentication
	Starting a conversation
	Sending Messages
	Receiving Messages

### Web Service
	Bot Framework Connector / Bot Framework Service
		REST API
			To access the Bot Connector service, use the serviceUrl value as the base URI for API requests. The serviceUrl is Channel based.
	Bot Message endpoints / Your Bot
		Service Resource
			Message endpoint
				The template implements a web service with a messaging endpoint. The service extracts the authentication header and request payload and forwards them to the adapter.
			Bot Adapter
				The adapter receives activities from the messaging endpoint, forwards them to the bot's turn handler, and catches any errors or exceptions the bot's logic doesn't catch.

The adapter allows you to add your own on turn error handler.
			Bot Object
				The bot object uses an activity handler and implements handlers for the activity types it will recognize and react to.

### More Info
	BotBuilder Samples
		C# ASP.NET Core MVC
		JS/TS Restify
		Java Spring
		Python AIOHTTP
