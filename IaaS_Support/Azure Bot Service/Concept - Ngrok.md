# Ngrok
   
[**ngrok**](https://ngrok.com/docs) is a cross-platform application that "allows you to expose a web server running on your local machine to the internet." Essentially, what we'll be doing is using **ngrok** to forward messages from external channels on the web directly to our local machine to allow debugging, as opposed to the standard messaging endpoint configured in the Azure portal.

### Usage:
1.  Open a terminal and navigate to the folder where your **ngrok** executable is.
    
2.  Run **ngrok** with the following command to create a new tunnel.
    
    cmdCopy
    
    ```
    ngrok http 3978 -host-header="localhost:3978"
    ```
    
     Note
    
    Please note that the port specified is the port your bot is running on. You may use any localhost port you'd like.
    
3.  When **ngrok** starts, copy and save the public forwarding URL for later.
    
    ![ngrok forwarding url](https://docs.microsoft.com/en-us/azure/bot-service/media/debug-ngrok/ngrok-forwarding-url.png?view=azure-bot-service-4.0)

More Info:
<[https://stackoverflow.com/questions/30535336/exposing-localhost-to-the-internet-via-tunneling-using-ngrok-http-error-400](https://stackoverflow.com/questions/30535336/exposing-localhost-to-the-internet-via-tunneling-using-ngrok-http-error-400)>

https://docs.microsoft.com/en-us/azure/bot-service/bot-service-debug-channel-ngrok?view=azure-bot-service-4.0