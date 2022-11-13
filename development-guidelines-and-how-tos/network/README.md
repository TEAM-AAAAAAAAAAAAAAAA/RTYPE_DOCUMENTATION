---
description: Description of the server, the client and the RFC
---

# 📡 Network

### Server

R-THAï is based on a UDP (User Datagram Protocol) protocol and created when executing the binary "r-type\_server".

All the game logic and the connexions are handled by the server and sent to the clients.

In order to start a server, you need to specify a port (8000 by default) in the entrypoint of the server part. The Server class is a singleton which run independently to the ECS.\
The server is asynchronous and the receiving IOService run in a thread.

Two LockedQueue (using mutexs) are responsible of the ingoing and outgoing data. In order to send data, you need to push a network::Message (wich is a std::array) into the outgoingQueue, incomming messages are handled in the HandleIncommingMessage class.

```cpp
network::Message msg;
//fill message
msg[0] = 0;
network::Server::getOutgoingMessages().push( 
network::ServerMessage(msg, std::vector()));
```

{% hint style="info" %}
src/ecs/systems/server/HandleIncommingMessage.hpp
{% endhint %}





### Client

A Client is created when executing the binary "r-type\_client" .

The menu permit you to select a room, or to set the options of your game like the sound volume.

The Client class is also a singleton using threads to hande incomming and outgoing data and work like the server (remember ingoing and outgoing lockedQueue ?).&#x20;

The client display every drawable entities from the server and himself (like the HUD) on the screen, and send the keyboards input to the server who handle them.

Because R-THAÏ is a multiplayer game, you can play on different client at the same time.





### Lobby

The lobby countain 4 rooms you can connect to. It interact with the client who can choose his room. It works by forking and executing the r-type\_server binary with different ports.

### RFC

The RFC (Request for comments) of our server/client protocol can be found here

{% content-ref url="rfc.md" %}
[rfc.md](rfc.md)
{% endcontent-ref %}
