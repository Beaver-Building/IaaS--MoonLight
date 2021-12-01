# Bot Analystics
Analytics is an extension of [Application Insights](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-analytics). Application Insights provides **service-level** and instrumentation data like traffic, latency, and integrations. Analytics provides **conversation-level** reporting on user, message, and channel data.

### Retention

Retention tracks how many users who sent one message came back later and sent another one. The chart is a rolling 10-day window; the results are not affected by changing the time frame.

![Retention chart](https://docs.microsoft.com/en-us/azure/bot-service/media/analytics-retention.png?view=azure-bot-service-4.0)

Note that the most recent possible date is two days ago; a user sent messages the day before yesterday and then _returned_ yesterday.

### [](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-manage-analytics?view=azure-bot-service-4.0#user)User

The Users graph tracks how many users accessed the bot using each channel during the specified time frame.

![Users graph](https://docs.microsoft.com/en-us/azure/bot-service/media/analytics-users.png?view=azure-bot-service-4.0)

-   The percentage chart shows what percentage of users used each channel.
-   The line graph indicates how many users were accessing the bot at a certain time.
-   The legend for the line graph indicates which color represents which channel and the includes the total number of users during the specified time period.

### [](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-manage-analytics?view=azure-bot-service-4.0#activities)Activities

The Activities graph tracks how many activities were sent and received using which channel during the specified time frame.

![activities graph](https://docs.microsoft.com/en-us/azure/bot-service/media/analytics-activities.png?view=azure-bot-service-4.0)

-   The percentage chart shows what percentage of activities were communicated over each channel.
-   The line graph indicates how many activities were sent and received over the specified time frame.
-   The legend for the line graph indicates which line color represents each channel and the total number of activities sent and received on that channel during the specified time period.