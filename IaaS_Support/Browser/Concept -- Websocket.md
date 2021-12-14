# Websocket

![[Pasted image 20211201160257.png]]

## JavaScript client example[[edit](https://en.wikipedia.org/w/index.php?title=WebSocket&action=edit&section=3 "Edit section: JavaScript client example")]

// Creates new WebSocket object with an ws URI as the parameter
const socket = new WebSocket('ws://game.example.com:12010/updates');

// Fired when a connection with a WebSocket is opened,
socket.onopen = function () {
  setInterval(function() {
    if (socket.bufferedAmount == 0)
      socket.send(getUpdateData());
  }, 50);
};

// Fired when data is received through a WebSocket,
socket.onmessage = function(event) {
  handleUpdateData(event.data);
};

// Fired when a connection with a WebSocket is closed,
socket.onclose = function(event) {
  onSocketClose(event);
};

// Fired when a connection with a WebSocket has been closed because of an error,
socket.onerror = function(event) {
  onSocketError(event);
};

## Web server implementation[[edit](https://en.wikipedia.org/w/index.php?title=WebSocket&action=edit&section=4 "Edit section: Web server implementation")]

[Nginx](https://en.wikipedia.org/wiki/Nginx "Nginx") has supported WebSockets since 2013, implemented in version 1.3.13 [[30]](https://en.wikipedia.org/wiki/WebSocket#cite_note-31) including acting as a [reverse proxy](https://en.wikipedia.org/wiki/Reverse_proxy "Reverse proxy") and [load balancer](https://en.wikipedia.org/wiki/Load_balancing_(computing) "Load balancing (computing)") of WebSocket applications.[[31]](https://en.wikipedia.org/wiki/WebSocket#cite_note-32)

[Apache HTTP Server](https://en.wikipedia.org/wiki/Apache_HTTP_Server "Apache HTTP Server") has supported WebSockets since July, 2013, implemented in version 2.4.5 [[32]](https://en.wikipedia.org/wiki/WebSocket#cite_note-33) [[33]](https://en.wikipedia.org/wiki/WebSocket#cite_note-34)

[Internet Information Services](https://en.wikipedia.org/wiki/Internet_Information_Services "Internet Information Services") added support for WebSockets in version 8 which was released with [Windows Server 2012](https://en.wikipedia.org/wiki/Windows_Server_2012 "Windows Server 2012").[[34]](https://en.wikipedia.org/wiki/WebSocket#cite_note-35)

[lighttpd](https://en.wikipedia.org/wiki/Lighttpd "Lighttpd") has supported WebSockets since 2017, implemented in version 1.4.46.[[35]](https://en.wikipedia.org/wiki/WebSocket#cite_note-36) [lighttpd](https://en.wikipedia.org/wiki/Lighttpd "Lighttpd") mod_proxy can act as a reverse proxy and load balancer of WebSocket applications. [lighttpd](https://en.wikipedia.org/wiki/Lighttpd "Lighttpd") mod_wstunnel can facilitate a WebSocket tunnel, allowing a client to employ WebSockets to tunnel a simpler protocol, such as [JSON](https://en.wikipedia.org/wiki/JSON "JSON"), to a backend application.

## Protocol handshake[[edit](https://en.wikipedia.org/w/index.php?title=WebSocket&action=edit&section=5 "Edit section: Protocol handshake")]

To establish a WebSocket connection, the client sends a WebSocket handshake request, for which the server returns a WebSocket handshake response, as shown in the example below.[[36]](https://en.wikipedia.org/wiki/WebSocket#cite_note-37)

Client request (just like in [HTTP](https://en.wikipedia.org/wiki/HTTP "HTTP"), each line ends with `[\r\n](https://en.wikipedia.org/wiki/%5Cr%5Cn "\r\n")` and there must be an extra blank line at the end):

GET /chat HTTP/1.1
Host: server.example.com
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Key: x3JJHMbDL1EzLkh9GBhXDw==
Sec-WebSocket-Protocol: chat, superchat
Sec-WebSocket-Version: 13
Origin: http://example.com

Server response:

HTTP/1.1 101 Switching Protocols
Upgrade: websocket
Connection: Upgrade
Sec-WebSocket-Accept: HSmrc0sMlYUkAGmm5OPpG2HaGWk=
Sec-WebSocket-Protocol: chat

The handshake starts with an HTTP request/response, allowing servers to handle HTTP connections as well as WebSocket connections on the same port. Once the connection is established, communication switches to a bidirectional binary protocol which does not conform to the HTTP protocol.

In addition to `Upgrade` headers, the client sends a `Sec-WebSocket-Key` header containing [base64](https://en.wikipedia.org/wiki/Base64 "Base64")-encoded random bytes, and the server replies with a [hash](https://en.wikipedia.org/wiki/Hash_function "Hash function") of the key in the `Sec-WebSocket-Accept` header. This is intended to prevent a [caching](https://en.wikipedia.org/wiki/Cache_(computing) "Cache (computing)") [proxy](https://en.wikipedia.org/wiki/HTTP_proxy "HTTP proxy") from re-sending a previous WebSocket conversation,[[37]](https://en.wikipedia.org/wiki/WebSocket#cite_note-38) and does not provide any authentication, privacy, or integrity. The hashing function appends the fixed string `258EAFA5-E914-47DA-95CA-C5AB0DC85B11` (a [UUID](https://en.wikipedia.org/wiki/UUID "UUID")) to the value from `Sec-WebSocket-Key` header (which is not decoded from base64), applies the [SHA-1](https://en.wikipedia.org/wiki/SHA-1 "SHA-1") hashing function, and encodes the result using base64.[[38]](https://en.wikipedia.org/wiki/WebSocket#cite_note-39)

The RFC6455 requires the key MUST be a nonce consisting of a randomly selected 16-byte value that has been base64-encoded,[[39]](https://en.wikipedia.org/wiki/WebSocket#cite_note-40) that is 24 bytes in [base64](https://en.wikipedia.org/wiki/Base64 "Base64") (with last two bytes to be `==`). Though some relaxed HTTP servers do allow shorter keys to present, many modern HTTP servers will reject the request with error "invalid Sec-WebSocket-Key header".

Once the connection is established, the client and server can send WebSocket data or text frames back and forth in [full-duplex](https://en.wikipedia.org/wiki/Duplex_(telecommunications) "Duplex (telecommunications)") mode. The data is minimally framed, with a small header followed by [payload](https://en.wikipedia.org/wiki/Payload_(computing) "Payload (computing)").[[40]](https://en.wikipedia.org/wiki/WebSocket#cite_note-41) WebSocket transmissions are described as "messages", where a single message can optionally be split across several data frames. This can allow for sending of messages where initial data is available but the complete length of the message is unknown (it sends one data frame after another until the end is reached and committed with the FIN bit). With extensions to the protocol, this can also be used for multiplexing several streams simultaneously (for instance to avoid monopolizing use of a socket for a single large payload).[[41]](https://en.wikipedia.org/wiki/WebSocket#cite_note-42)