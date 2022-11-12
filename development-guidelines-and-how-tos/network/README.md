---
description: Description of the server, the client and the RFC
---

# 📡 Network

### Server

R-THAï is based on a UDP (User Datagram Protocol) protocol and created when executing the binary "r-type\_server".

All the game logic and the connexions are handled by the server and sent to the clients.

In order to start a server, you need to specify a port (8000 by default) in the entrypoint of the server part. The Server class is a singleton which run independently to the ECS.\
The server is asynchronous and the receiving IOService run in a thread.

\


### Client

A Client is created when executing the binary "r-type\_client" and a menu appears.

All the display and keyboard inputs are handled by the client.

In order to start a client, you need to specify a port (8000 by default) and a host (localhost by default) in the getGameWorld function (getWorld.cpp). The Client class is also a singleton using threads to hande incomming and outgoing data.&#x20;

We will see how to change port and host in the Asset and Keys



### RFC

The RFC (Request for comments) of our server/client protocol can be found here

{% content-ref url="rfc.md" %}
[rfc.md](rfc.md)
{% endcontent-ref %}
