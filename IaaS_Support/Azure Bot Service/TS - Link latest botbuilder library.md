# Link latest botbuilder library

To get started building bots using the SDK, see the [Azure Bot Service Documentation](https://docs.microsoft.com/en-us/azure/bot-service/?view=azure-bot-service-4.0).

The [Bot Framework Samples](https://github.com/microsoft/botbuilder-samples) includes a rich set of samples repository.

If you want to debug an issue, would like to [contribute](https://github.com//microsoft/botbuilder-js#Contributing-and-our-code-of-conduct), or understand how the Bot Builder SDK works, instructions for building and testing the SDK are below.

### [](https://github.com//microsoft/botbuilder-js#prerequisites)Prerequisites

-   [Git](https://git-scm.com/downloads)
-   [Node.js](https://nodejs.org/en/)
-   [Yarn 1.x](https://classic.yarnpkg.com/)
-   Your favorite [VS Code](https://code.visualstudio.com/)

Clone a copy of the repo:

`git clone https://github.com/microsoft/botbuilder-js.git`

Change to the SDK's directory:

`cd botbuilder-js`

Install the prerequisites.

`yarn`

Then use the following command to build the SDK.

`yarn build`

Link botbuilder package to sample

`cd libraries/botbuilder
yarn link
cd path_to_your_project
yarn link botbuilder
`

Rebuild your bot and restart bot

`yarn`