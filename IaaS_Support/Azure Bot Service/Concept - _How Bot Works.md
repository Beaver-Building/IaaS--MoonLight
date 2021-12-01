# How Bot Works
   

Channels <-> Bot Framework Service(Connector) <-> The Bot(Web App Bot)

Simply speaking, when a message from different channels, reaches corresponding bot framework service, the service will do the schema transformation, and deliver the message to your bot. likewise, when the bot responds to each message, it sends the message back to Framework service, and the framework service will then send it to original channel.

![[Pasted image 20210713164703.png]]

   

So, how to find your bot? there is a message endpoint defined for your bot, usually it's [https://*websitename*/api/messages](https://*websitename*/api/messages)

How bot works: [How bots work - Bot Service | Microsoft Docs](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-basics?view=azure-bot-service-4.0)

Scenerio

A bot can be thought of as a web application that has a conversational interface.

Service

The main part of bot application is conversation flow:

Procedural conversation flow

Handle interruptions

handoff to human

Expire a conversation

Additionally, bots may use other services, such as:

Azure Cognitive Services to build intelligent applications (LUIS, QnA)

Azure Storage for cloud storage solution

Rich Card Attachments

Other 3rd Party APIs

Storage

Storage layer is where the state information is actually stored. This can be thought of as your physical storage, such as in-memory, Azure, or a third party server.

The Bot Framework SDK includes some implementations for the storage layer:

Memory storage implements in-memory storage for testing purposes. In-memory data storage is intended for local testing only as this storage is volatile and temporary. The data is cleared each time the bot is restarted.

Azure Blob Storage connects to an Azure Blob Storage object database.

Azure Cosmos DB partitioned storage connects to a partitioned Cosmos DB NoSQL database.

Other storage are also availble: [write directly to storage](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-howto-v4-storage?view=azure-bot-service-4.0)

Appendix

Test -- Bots are complex apps with a lot of different parts working together. Like any other complex app, this can lead to some interesting bugs or cause your bot to behave differently than expected. Before publishing, test your bot. We provide several ways to test bots before they are released for use:

Test your bot locally with the emulator. The Bot Framework Emulator is a stand-alone app that not only provides a chat interface but also debugging and interrogation tools to help understand how and why your bot does what it does. The Emulator can be run locally alongside your in-development bot application.

Test your bot on the web. Once configured through the Azure portal your bot can also be reached through a web chat interface. The web chat interface is a great way to grant access to your bot to testers and other people who do not have direct access to the bot's running code.

Unit Test your bot with the current Bot Framework SDK.

Evaluate -- Use the data collected in Azure portal to identify opportunities to improve the capabilities and performance of your bot. You can get service-level and instrumentation data like traffic, latency, and integrations. Analytics also provides conversation-level reporting on user, message, and channel data. For more information, see how to gather analytics.

Publish -- When you are ready for your bot to be available on the web, publish your bot to Azure or to your own web service or data center. Having an address on the public internet is the first step to your bot coming to life on your site, or inside chat channels

Manage bot resource with .bot, .env, [https://docs.microsoft.com/en-us/azure/bot-service/bot-file-basics?view=azure-bot-service-4.0&tabs=csharp](https://docs.microsoft.com/en-us/azure/bot-service/bot-file-basics?view=azure-bot-service-4.0&tabs=csharp)