# Bot Storage and Custom Storage

   

Bot Service utilizes Azure storage technologies to persist Bot configuration data that are geo-replicated to multiple geos around the world for high availability/low latency. Customer data in these long term stores are double encrypted, and in the case of CMK, encrypted also with the customer's key in lieu of the second system managed key.

In the case of DirectLine/Webchat channel, some other data associated with messaging (including message body and/or attachments) is temporarily stored near to the place where the conversation started in our system for up to 24 hours for reliable delivery, after which time it is deleted.  Because it's stored briefly, this is encrypted with our double encryption using system managed keys.

Besides, we do not have granular data for message traffic beyond 90 days. Since we bill for only activities of type “message”.  We could theoretically extract the billing data, but that won’t give us any new insight as that is “post aggregation” and is what’s used to generate the customer’s bill, but has no detail other than what you see in your invoice.



## Composer using Custom Storag
  
 blobStorage is used to enable TranscriptLoggerMiddleware.

cosmosDb is used to store user and conversation data.

applicationInsights is used to enable the telemetry logger.


Provision:

cosmosdb and blob provision feature are released in version 2.1.0

feat: provisioning services for qna, bot registration, luis, cosmosdb, blob storage #[8321](https://github.com/microsoft/BotFramework-Composer/pull/8321)

Configuration:

To use configure telemetry, you need to configure “telemetry” and “cosmosDb” as following:

  ![[Pasted image 20210818175312.png]]

To use transcript logging middleware, you need to enable ‘traceTranscript’ and configure ‘blobTranscript’ in the runtimeSettings.

 ![[Pasted image 20210818175325.png]]

[https://github.com/microsoft/BotFramework-Composer/issues/3286](https://github.com/microsoft/BotFramework-Composer/issues/3286)

blobStorage is used to enable TranscriptLoggerMiddleware.

cosmosDb is used to store user and conversation data.

applicationInsights is used to enable the telemetry logger.