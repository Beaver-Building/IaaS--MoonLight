# Bot Channel Facebook


I used an sample connected to [Facebook Channel](https://docs.microsoft.com/en-us/azure/bot-service/channel-connect-teams?view=azure-bot-service-4.0) throughout the article for instruction.

[ngrok](https://ngrok.com/docs) is a cross-platform application that "allows you to expose a web server running on your local machine to the internet."

Essentially, what we'll be doing is using ngrok to forward messages from external channels on the web directly to our local machine to allow debugging.

1.  Open a terminal and navigate to the folder where your ngrok executable is.
2.  Run ngrok with the following command to create a new tunnel.

ngrok http 3978 -host-header="localhost:3978"
![[Pasted image 20210818201055.png]]

   

1.  While ngrok is running, login to your Azure portal and view your bot settings.
2.  Select your Bot Channels Registration connected to your local bot.
3.  Scroll down to Configuration. Copy and paste the ngrok forwarding URL in the Messaging endpoint field. Ensure that you maintain "/api/messages" at the end of the URL.

![[Pasted image 20210818201115.png]]

   

1.  Scroll up and select Save.
2.  At this point, incoming messages from to your bot from external channels will now be sent to your local bot. The sample bot we'll use to demonstrate this is already configured live for the channel.

![[Pasted image 20210818201204.png]]

   

Debug

1.  Locally, you can set breakpoints in Visual Studio. Expanding the text property from the incoming activity object, you will see that the message you sent the bot from teams is being intercepted locally for you to debug.
2.  From here you can debug normally and run your code step by step. You can use this to debug your bot from any channel.