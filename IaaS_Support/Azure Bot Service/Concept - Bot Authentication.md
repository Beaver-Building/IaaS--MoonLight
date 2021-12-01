# Bot Authentication
   
## Azure Bot Service Authentication
Usually when we talk about bot authentication, it has two different scenarios, and these two actually are totally different and irrelevant:

1.  To use bot service, it requires to register AAD app registration, this is to manage the access to bot framework service(connector) from your bot and vice versa. Usually you will get APP ID and password when creating Bot in Azure. We can call this Bot authentication.
2.  To enrich the functionality of bot, you may need to access different resources, to secure these connections, you may ask your users to login before start use the bot. we can call this OAuth connection.

-   Bot authentication:

Your bot communicates with the Bot Connector service using HTTP over a secured channel (SSL/TLS). When your bot sends a request to the Connector service, it must include information that the Connector service can use to verify its identity. Likewise, when the Connector service sends a request to your bot, it must include information that the bot can use to verify its identity.

If you are using the [Bot Framework SDK for .NET](https://docs.microsoft.com/en-us/azure/bot-service/dotnet/bot-builder-dotnet-overview?view=azure-bot-service-4.0) or the [Bot Framework SDK for Node.js](https://docs.microsoft.com/en-us/azure/bot-service/nodejs/?view=azure-bot-service-4.0), you do not need to implement the security procedures described in this article, because the SDK automatically does it for you. Simply configure your project with the App ID and password that you obtained for your bot during [registration](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-quickstart-registration?view=azure-bot-service-4.0) and the SDK will handle the rest.

For troubleshooting purpose, if you received 401 when using bot, you always need to check the app ID and password configurations first.

Optional: To further understand how bot authentication works, refer: [Authenticate requests - Bot Service | Microsoft Docs](https://docs.microsoft.com/en-us/azure/bot-service/rest-api/bot-framework-rest-connector-authentication?view=azure-bot-service-4.0)

-   OAuth connection:

At times a bot must access secured online resources on behalf of the user, such as checking email, checking on flight status, or placing an order. The user must authorize the bot to do so on their behalf, and in order to authorize the bot, the user must authenticate their identity. OAuth is used to authenticate the user and authorize the bot.

To secure the call to an external service, the bot must ask the user to sign-in, so it can acquire the user's token for that service. Many services support token retrieval via the OAuth or OAuth2 protocol. To achieve this, bot admins need to add extra oauth connection in Azure and add it into bot application.

1.  How to add oauth for bot: [Add authentication to a bot via Azure Bot Service - Bot Service | Microsoft Docs](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-authentication?view=azure-bot-service-4.0&tabs=aadv2%2Ccsharp#register-the-azure-ad-identity-provider-with-the-bot)
2.  How it works: [User authentication in the Azure Bot Service - Bot Service | Microsoft Docs](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-concept-authentication?view=azure-bot-service-4.0#user-authentication-in-a-conversation)

Troubleshooting guidance:

For both of them, if we find authentication failure, we could engage engineer from AAD team to assist.

## Teams Bot Authentication
OAuth 2.0 is an open standard for authentication and authorization used by Azure Active Directory (Azure AD) and many other identity providers. A basic understanding of OAuth 2.0 is a prerequisite for working with authentication in Teams; [here's a good overview](https://aaronparecki.com/oauth-2-simplified/) that's easier to follow than the [formal specification](https://oauth.net/2/). Authentication flow for tabs and bots is a little different — tabs are very similar to websites so they can use OAuth 2.0 directly, while bots aren't and must do a few things differently — but the core concepts are identical.

See the GitHub repo [Microsoft Teams Authentication Sample](https://github.com/OfficeDev/Microsoft-Teams-Samples/tree/main/samples/app-auth/nodejs) for an example that demonstrates authentication flow for bots using Node.js and the [OAuth 2.0 authorization code grant type](https://oauth.net/2/grant-types/authorization-code/).

![[Pasted image 20210818172926.png]]

1.  The user sends a message to the bot.
    
2.  The bot determines if the user needs to sign in. In this example, the bot stores the access token in its user data store. It asks the user to sign in if it doesn't have a validated token for the selected identity provider. ([View code](https://github.com/OfficeDev/microsoft-teams-sample-auth-node/blob/469952a26d618dbf884a3be53c7d921cc580b1e2/src/utils/AuthenticationUtils.ts#L58-L76))
    
3.  The bot constructs the URL to the start page of the authentication flow, and sends a card to the user with a `signin` action. ([View code](https://github.com/OfficeDev/microsoft-teams-sample-auth-node/blob/469952a26d618dbf884a3be53c7d921cc580b1e2/src/dialogs/BaseIdentityDialog.ts#L160-L190))  
    Like other application auth flows in Teams, the start page must be in a domain that's on your `validDomains` list, and in the same domain as the post-login redirect page.
    
     Important
    
    The OAuth 2.0 authorization code grant flow calls for a `state` parameter in the authentication request which contains a unique session token to prevent a [cross-site request forgery attack](https://en.wikipedia.org/wiki/Cross-site_request_forgery). The example uses a randomly-generated GUID.
    
4.  When the user selects the _signin_ button, Teams opens a popup window and navigates to the start page.
5.  The start page redirects the user to the identity provider's `authorize` endpoint. ([View code](https://github.com/OfficeDev/microsoft-teams-sample-auth-node/blob/469952a26d618dbf884a3be53c7d921cc580b1e2/public/html/auth-start.html#L51-L56))
6.  On the provider's site, the user signs in and grants access to the bot.
7.  The provider takes the user to the bot's OAuth redirect page with an authorization code.
8.  The bot redeems the authorization code for an access token, and **provisionally** associates the token with the user that initiated the sign-in flow. Below, we call this a _provisional token_.
9.   The OAuth callback renders a page that calls `notifySuccess("<verification code>")`. ([View code](https://github.com/OfficeDev/microsoft-teams-sample-auth-node/blob/master/src/views/oauth-callback-success.hbs))
    
10.  Teams closes the pop-up window and sends the `<verification code>` sent to `notifySuccess()` back to the bot. The bot receives an [invoke](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-activities#invoke) message with `name = signin/verifyState`.
    
11.  The bot checks the incoming verification code against the verification code stored with the user's provisional token. ([View code](https://github.com/OfficeDev/microsoft-teams-sample-auth-node/blob/469952a26d618dbf884a3be53c7d921cc580b1e2/src/dialogs/BaseIdentityDialog.ts#L127-L140))
    
12.  If they match, the bot marks the token as validated and ready for use. Otherwise, the auth flow fails, and the bot deletes the provisional token.

More info: 
https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-authentication-basics?view=azure-bot-service-4.0

https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-concept-authentication-types?view=azure-bot-service-4.0

https://docs.microsoft.com/en-us/microsoftteams/platform/bots/how-to/authentication/auth-flow-bot