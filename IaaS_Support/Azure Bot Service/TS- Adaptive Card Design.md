  # Adaptive Card Design
  
 Adaptive Cards are an open card exchange format enabling developers to exchange UI content in a common and consistent way.
  
[**Card Authors**](https://docs.microsoft.com/en-us/adaptive-cards/authoring-cards/getting-started) describe their content as a simple JSON object. That content can then be rendered natively inside a [**Host Application**](https://docs.microsoft.com/en-us/adaptive-cards/rendering-cards/getting-started), automatically adapting to the look and feel of the Host.

More Info:
[https://adaptivecards.io/designer](https://adaptivecards.io/designer)

[https://adaptivecards.io/explorer/](https://adaptivecards.io/explorer/)

# Adaptive Card Action
   

[https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)

Class CardAction

Builder class to simplify adding actions to a card.

Hierarchy

-   CardAction

Implements

-   [IIsCardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/interfaces/_botbuilder_d_.iiscardaction.html)

Index

Constructors

-   [constructor](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#constructor)

Methods

-   [image](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#image)
-   [title](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#title)
-   [toAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#toaction)
-   [type](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#type)
-   [value](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#value)
-   [call](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#call)
-   [dialogAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#dialogaction)
-   [downloadFile](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#downloadfile)
-   [imBack](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#imback)
-   [openUrl](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#openurl)
-   [playAudio](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#playaudio)
-   [playVideo](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#playvideo)
-   [postBack](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#postback)
-   [showImage](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#showimage)

Constructors

constructor

-   new CardAction(session?: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html)): [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)
-   Defined in [botbuilder.d.ts:2127](https://github.com/Microsoft/BotBuilder/blob/7b70cfd/Node/core/lib/botbuilder.d.ts#L2127)  
    Creates a new CardAction.  
    Parameters
-   Optional session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html)  
    (Optional) will be used to localize any text.  
    Returns [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)

Methods

image

-   image(url: string): [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)
-   Defined in [botbuilder.d.ts:2145](https://github.com/Microsoft/BotBuilder/blob/7b70cfd/Node/core/lib/botbuilder.d.ts#L2145)  
    For buttons an image to include next to the buttons label. Not supported by all channels.  
    Parameters
-   url: string  
    Returns [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)

title

-   title(text: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype), ...args: any[]): [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)
-   Defined in [botbuilder.d.ts:2139](https://github.com/Microsoft/BotBuilder/blob/7b70cfd/Node/core/lib/botbuilder.d.ts#L2139)  
    Title of the action. For buttons this will be the label of the button. For tap actions this may be used for accesibility purposes or shown on hover.  
    Parameters
-   text: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)
-   Rest ...args: any[]  
    Returns [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)

toAction

-   toAction(): [ICardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/interfaces/_botbuilder_d_.icardaction.html)
-   Implementation of [IIsCardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/interfaces/_botbuilder_d_.iiscardaction.html).[toAction](https://docs.botframework.com/en-us/node/builder/chat-reference/interfaces/_botbuilder_d_.iiscardaction.html#toaction)
-   Defined in [botbuilder.d.ts:2148](https://github.com/Microsoft/BotBuilder/blob/7b70cfd/Node/core/lib/botbuilder.d.ts#L2148)  
    Returns the JSON for the action.  
    Returns [ICardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/interfaces/_botbuilder_d_.icardaction.html)

type

-   type(t: string): [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)
-   Defined in [botbuilder.d.ts:2136](https://github.com/Microsoft/BotBuilder/blob/7b70cfd/Node/core/lib/botbuilder.d.ts#L2136)  
    Type of card action.  
    Parameters
-   t: string  
    Returns [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)

value

-   value(v: string): [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)
-   Defined in [botbuilder.d.ts:2142](https://github.com/Microsoft/BotBuilder/blob/7b70cfd/Node/core/lib/botbuilder.d.ts#L2142)  
    The actions value.  
    Parameters
-   v: string  
    Returns [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)

Static call

-   call(session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html), number: string, title?: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)): [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)
-   Defined in [botbuilder.d.ts:2154](https://github.com/Microsoft/BotBuilder/blob/7b70cfd/Node/core/lib/botbuilder.d.ts#L2154)  
    Places a call to a phone number. The should include country code in +44/+1 format for Skype calls.  
    Parameters
-   session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html)  
    (Optional) Current session object for the conversation. If specified will be used to localize titles.
-   number: string
-   Optional title: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)  
    Returns [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)

Static dialogAction

-   dialogAction(session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html), action: string, data?: string, title?: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)): [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)
-   Defined in [botbuilder.d.ts:2212](https://github.com/Microsoft/BotBuilder/blob/7b70cfd/Node/core/lib/botbuilder.d.ts#L2212)  
    Binds a button or tap action to a named action registered for a dialog or globally off the bot.  
    Can be used anywhere a [postBack](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#postback) is valid. You may also statically bind a button to an action for something like Facebooks [Persistent Menus](https://developers.facebook.com/docs/messenger-platform/thread-settings/persistent-menu). The payload for the button should be action?<action> for actions without data or action?<action>=<data> for actions with data.Parameters
-   session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html)  
    (Optional) Current session object for the conversation. If specified will be used to localize titles.
-   action: string  
    Name of the action to invoke when tapped.
-   Optional data: string  
    (Optional) data to pass to the action when invoked. The [IRecognizeActionResult.data](https://docs.botframework.com/en-us/node/builder/chat-reference/interfaces/_botbuilder_d_.irecognizeactionresult#data) property can be used to access this data. If using [beginDialogAction()](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/dlg./en-us/node/builder/chat-reference/classes/_botbuilder_d_.dialog#begindialogaction) this value will be passed as part of the dialogs initial arguments.
-   Optional title: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)  
    (Optional) title to assign when binding the action to a button.  
    Returns [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)

Static downloadFile

-   downloadFile(session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html), url: string, title?: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)): [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)
-   Defined in [botbuilder.d.ts:2196](https://github.com/Microsoft/BotBuilder/blob/7b70cfd/Node/core/lib/botbuilder.d.ts#L2196)  
    Downloads the specified file to the users device. Not currently supported for Skype.  
    Parameters
-   session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html)  
    (Optional) Current session object for the conversation. If specified will be used to localize titles.
-   url: string
-   Optional title: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)  
    Returns [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)

Static imBack

-   imBack(session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html), msg: string, title?: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)): [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)
-   Defined in [botbuilder.d.ts:2166](https://github.com/Microsoft/BotBuilder/blob/7b70cfd/Node/core/lib/botbuilder.d.ts#L2166)  
    Sends a message to the bot for processing in a way that's visible to all members of the conversation. For some channels this may get mapped to a [postBack](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#postback).  
    Parameters
-   session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html)  
    (Optional) Current session object for the conversation. If specified will be used to localize titles.
-   msg: string
-   Optional title: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)  
    Returns [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)

Static openUrl

-   openUrl(session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html), url: string, title?: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)): [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)
-   Defined in [botbuilder.d.ts:2160](https://github.com/Microsoft/BotBuilder/blob/7b70cfd/Node/core/lib/botbuilder.d.ts#L2160)  
    Opens the specified URL.  
    Parameters
-   session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html)  
    (Optional) Current session object for the conversation. If specified will be used to localize titles.
-   url: string
-   Optional title: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)  
    Returns [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)

Static playAudio

-   playAudio(session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html), url: string, title?: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)): [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)
-   Defined in [botbuilder.d.ts:2178](https://github.com/Microsoft/BotBuilder/blob/7b70cfd/Node/core/lib/botbuilder.d.ts#L2178)  
    Plays the specified audio file to the user. Not currently supported for Skype.  
    Parameters
-   session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html)  
    (Optional) Current session object for the conversation. If specified will be used to localize titles.
-   url: string
-   Optional title: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)  
    Returns [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)

Static playVideo

-   playVideo(session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html), url: string, title?: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)): [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)
-   Defined in [botbuilder.d.ts:2184](https://github.com/Microsoft/BotBuilder/blob/7b70cfd/Node/core/lib/botbuilder.d.ts#L2184)  
    Plays the specified video to the user. Not currently supported for Skype.  
    Parameters
-   session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html)  
    (Optional) Current session object for the conversation. If specified will be used to localize titles.
-   url: string
-   Optional title: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)  
    Returns [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)

Static postBack

-   postBack(session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html), msg: string, title?: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)): [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)
-   Defined in [botbuilder.d.ts:2172](https://github.com/Microsoft/BotBuilder/blob/7b70cfd/Node/core/lib/botbuilder.d.ts#L2172)  
    Sends a message to the bot for processing in a way that's hidden from all members of the conversation. For some channels this may get mapped to a [imBack](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html#imback).  
    Parameters
-   session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html)  
    (Optional) Current session object for the conversation. If specified will be used to localize titles.
-   msg: string
-   Optional title: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)  
    Returns [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)

Static showImage

-   showImage(session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html), url: string, title?: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)): [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)
-   Defined in [botbuilder.d.ts:2190](https://github.com/Microsoft/BotBuilder/blob/7b70cfd/Node/core/lib/botbuilder.d.ts#L2190)  
    Opens the specified image in a native image viewer. For Skype only valid as a tap action on a CardImage.  
    Parameters
-   session: [Session](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.session.html)  
    (Optional) Current session object for the conversation. If specified will be used to localize titles.
-   url: string
-   Optional title: [TextType](https://docs.botframework.com/en-us/node/builder/chat-reference/modules/_botbuilder_d_.html#texttype)

Returns [CardAction](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)

From <[https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html](https://docs.botframework.com/en-us/node/builder/chat-reference/classes/_botbuilder_d_.cardaction.html)>