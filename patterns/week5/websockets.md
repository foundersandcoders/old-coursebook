#Web Sockets
**_Websocket_** is a protocol which allows the creation of two way persistant connections between a server and a client.

**_WebSockets_** represent a long awaited evolution in client/server web technology. 
They allow a long-held single TCP socket connection to be established between the client and server 
which allows for full duplex, messages to be instantly distributed with little overhead resulting in a very low latency connection.
This allows greater ability of the server to communicate with the clients. 

In a full duplex system, both parties can communicate with each other simultaneously. 
An example of a full-duplex device is a telephone; 
the parties at both ends of a call can speak and be heard by the other party simultaneously. 
eg. the server can send information as an event object without waiting for a request from the client.

####Why WebSockets are a game-changer
Finally WebSockets represent a standard for bi-directional realtime communication between servers and clients. 
Firstly in web browsers, but ultimately between any server and any client. 
The standards first approach means that as developers we can finally create functionality that 
works consistently across multiple platforms. Connection limitations are no longer a problem 
since WebSockets represent a single TCP socket connection. 
Cross domain communication has been considered from day one and is dealt with within the connection handshake.
This means that services such as Pusher can easily use them when offering a massively scalable realtime platform that 
can be used by any website, web, desktop or mobile application.

####How are they different to http request/response patterns?
With http once a request has been made the connection between the server and the client side is now closed. 
When using websocket.io it keeps an open connection until the tab has been refreshed or closed. 
This means there is a continuos two connection between client and server.

####Practicle example
We recommend following this short tutorial on making a realtime chatroom with socket.io to understand a practical application: [chat room tutorial](http://socket.io/get-started/chat/)

####Recommended Reading
https://pusher.com/websockets

https://en.wikipedia.org/wiki/WebSocket

http://socket.io/






