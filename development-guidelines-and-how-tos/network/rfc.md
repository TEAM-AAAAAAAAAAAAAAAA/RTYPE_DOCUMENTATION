---
description: R-THAAAAAAÏ network protocol documentation
---

# RFC

## Introduction

### How work the update of the game

Every x ticks, all the game is resend to the client so that no roll back may cause a desync, else all the entities that have been updated are send. Packet types shouldn't represent where they come from, they should be universal.

### Words and meanings:

```
EntityNetworkId -> 2 byte binary of the entity's ID
PosX -> 2 byte binary of the horizontal position
PosY -> 2 byte binary of the vertical position
Width -> 1 byte binary of the entity's width
Height -> 1 byte binary of the entity's height
TypeId -> 1 byte binary of the entity's type ID
VelocityX -> 1 byte binary of the horizontal velocity of entity
VelocityY -> 1 byte binary of the vertical velocity of entity
ClientName -> 4 bytes of chars that identify the player
```

### Order of bytes:

In order to stay consistant with the information that is received and sent, we have decided to follow this template for all packets.

```
<packet type>(<ClientName>)(<EntityNetworkId>)(<TypeId>)(<PosX><PosY>)(<Width><Height>)(<VelocityX><VelocityY>)
```

## Universal

### Keep Alive Request

Keep alive response request, asks the other side of the connection for a packet to ensure that it is still alive

```
    Packet type: 01000110 (70)
```

### Keep Alive Response

Response to the KA request

```
    Packet type: 01000111 (71)
```

## Client to Hub Server

In order for the client to connect to a room, they must first connect to the main server in order to get the current list of rooms.

### Connection

Client connects to the hub

```
Packet type: 00000000 (0)
```

Client creates to a room

```
Packet type: 11111110 (254)
```

Client connects to a room

```
Packet type: 11111111 (255)
    EntityNetworkId: 2 byte
```

### Request room information

Client refreshes server list

```
Packet type: 10000000 (128)
```

## Hub Server to Client

### Connection

Client connects to the lobby

```
Packet type: 01000000 (64)
    
```

### Room info

```
Packet type: 10000001 (129)
    EntityNetworkId: 2 byte
    Availability: 1 byte
```

## Hub to Room

Hub connects to room for the first time

```
Packet type: 01000100 (68)
```

### Room check

```
Packet type: 01111111 (127)
```

## Room to Hub

```
Packet type: 10000001 (129)
    Availability: 1 byte
```

## Room to Hub

Response to hub connecting to room

```
Packet type: 01000101 (69)
```

### Room info

```
Packet type: 10000010 (130)
    Availability: 1 byte
```

## Client to Room

### Connection

Client connects to server for first time

```
Packet type: 00000000 (0)
```

### Client sends an input to the Room Server

Moved player to position:

```
Packet type: 00000001 (1)
    PosX: 2 byte
    PosY: 2 byte
```

Client shot:

```
Packet type: 00000010 (2)
```

Client Charged Shot:

```
Packet type: 00000100 (4)
```

## Room to Client

### Connection

Server responds to client connecting for first time

```
Packet type: 00000000 (0)
    EntityNetworkId: 2 byte
```

### Server updates on movement

Movement of Entity:

```
Packet type: 00001000 (8)
    EntityNetworkId: 2 byte
    TypeId: 1 byte
    PosX: 2 bytes
    PosY: 2 bytes
    Width: 1 byte
    Height: 1 byte
    VelocityX: 1 byte
    VelocityY: 1 byte
```

### Server on player health

Health of player:

```
Packet type: 100110 (38)
    Health: 1 byte
```
