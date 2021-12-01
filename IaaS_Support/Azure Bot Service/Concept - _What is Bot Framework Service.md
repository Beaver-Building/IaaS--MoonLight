# _What is Bot Framework Service

The Bot Framework Service, which is a component of the Azure Bot Service, sends information between the user's bot-connected app (such as Facebook or Slack and so on, which we call the channel) and the bot. Each channel may include additional information in the activities they send.

For each channel, MS provides its own service, usually it's running on Azure App Service, with endpoint like:

-   webchat.botframework.com
-   directline.botframework.com
-   facebook.botframework.com
-   email.botframework.com, etc.

However, the situation is different for First Party channel, including Teams/SFB.

Bot will leverage its own service for message delivery. This will also be noticed when we do bot troubleshooting.

Activities

Every interaction between the user (or a channel) and the bot is represented as an activity. The Bot Framework Activity schema defines the activities that can be exchanged between a user or channel and a bot. Activities can represent human text or speech, app-to-app notifications, reactions to other messages, and so on.

Turns

In a conversation, people often speak one-at-a-time, taking turns speaking. With a bot, it generally reacts to user input. Within the Bot Framework SDK, a turn consists of the user's incoming activity to the bot and any activity the bot sends back to the user as an immediate response. You can think of a turn as the processing associated with the bot receiving a given activity.

For example, a user might ask a bot to perform a certain task. The bot might respond with a question to get more information about the task, at which point this turn ends. On the next turn, the bot receives a new message from the user that might contain the answer to the bot's question, or it might represent a change of subject or a request to ignore the initial request to perform the task.