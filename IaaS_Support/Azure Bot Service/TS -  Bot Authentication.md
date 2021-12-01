# Bot Authentication Q&A

   

The multi-tenant organization is what enables the Azure Bot Service servers (in the [botframework.com](http://botframework.com/) tenant) to authenticate requests coming from the bot (registered in the customer's tenant) through our servers. It's part of our service to service authentication protocol. it is not used for other purposes, and not to have any claims added to it for other access.

To authenticate users, you should utilize the user auth features in the bot service, you can sign in to AAD or Auth based authentication servers if you prefer.