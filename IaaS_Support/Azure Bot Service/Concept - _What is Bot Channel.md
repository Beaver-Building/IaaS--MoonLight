# _What is Bot Channel

   

A channel is a connection between communication applications and a bot. A bot, registered with Azure, uses channels to facilitate the communication with users.

## Current channels available:

[Alexa](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-channel-connect-alexa?view=azure-bot-service-4.0) 

Communicate with users through Alexa devices that support Custom Skills.

[Direct Line](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-channel-directline?view=azure-bot-service-4.0)

Integrate a bot into a mobile app, web page, or other applications.

[Office 365 email](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-channel-connect-email?view=azure-bot-service-4.0)

Enable a bot to communicate with users via Office 365 email.

[Facebook](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-channel-connect-facebook?view=azure-bot-service-4.0)

Connect a bot to both Facebook Messenger and Facebook Workplace, so that it can communicate with users on both platforms.

[Kik](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-channel-connect-groupme?view=azure-bot-service-4.0)

Configure a bot to communicate with users through the Kik messaging app.

[LINE](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-channel-connect-line?view=azure-bot-service-4.0)

Configure a bot to communicate with users through the LINE app.

[Microsoft Teams](https://docs.microsoft.com/en-us/azure/bot-service/channel-connect-teams?view=azure-bot-service-4.0)

Configure a bot to communicate with users through Microsoft Teams.

[Skype](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-channel-connect-skype?view=azure-bot-service-4.0)

Configure a bot to communicate with users through Skype.

[Skype for Business](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-channel-connect-skypeforbusiness?view=azure-bot-service-4.0)

Configure a bot to communicate with users through Skype for Busines.

[Slack](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-channel-connect-slack?view=azure-bot-service-4.0)

Configure a bot to communicate with users through Slack.

[Telegram](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-channel-connect-telegram?view=azure-bot-service-4.0)

Configure a bot to communicate with users through Telegram.

[Telephony](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-channel-connect-telephony?view=azure-bot-service-4.0)

Configure a bot to communicate with users through the Bot Framework Telephony channel.

[Twilio](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-channel-connect-twilio?view=azure-bot-service-4.0)

Configure a bot to communicate with users through the Twilio cloud communication platform.

[WeChat](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-channel-connect-wechat?view=azure-bot-service-4.0)

Configure a bot to communicate with users using the WeChat platform.

[Web Chat](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-channel-connect-webchat?view=azure-bot-service-4.0)

Automatically configured for you when you create a bot with the Bot Framework Service.

[Webex](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-adapter-connect-webex?view=azure-bot-service-4.0)

Configure a bot to communicate with users using the Webex.

[Additional channels](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-channel-additional-channels?view=azure-bot-service-4.0)

Additional channels available as an adapter through [provided platforms](https://botkit.ai/docs/v4/platforms/) via Botkit and [community repositorie](https://botkit.ai/docs/v4/platforms/)


  

## BOT Schema Transformation:

 a channel converts incoming messages from other services to the Bot Framework protocol schema. Likewise, messages sent by the bot to other services are transformed from the Bot Framework native schema to the format of these services. This process is called schema transformation. The Bot Framework Service maintains backward compatibility of the protocol in order to avoid changing behavior of the existing bots.

Supported schema transformation versions:

-   Version 1.3

Date introduced: May 2021

Changes:

Direct Line: Remove Deserialize/Reserialize of Adaptive Cards. The content of Adaptive Cards will be passed to the client as is.

-   Version 1.2

Date introduced: April 2021

Changes:

Slack channel: Attachment name is used for Message Text value.

Facebook channel: Upgrade to [Facebook Graph API v9.0](https://developers.facebook.com/docs/graph-api/changelog/version9.0/).

-   Version 1.1

Date introduced: April 2021

Changes:

Telegram channel: Use [MarkdownV2 syntax](https://core.telegram.org/bots/api#markdownv2-style) for all markdown.

-   Version 1.0

Original version
