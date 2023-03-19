# Chat

## Introduction
In this project, we would like to implement a simple chat using UDP Protocol. Our chat will behave in a similar way to a WhatsApp group, where any member of the group can write, and every message someone writes is sent to all members of the group. Please note, when someone sends a message to the group - the message is sent to the server immediately. However, the server will send the appropriate messages to clients only when they contact the server.

## Table of contents
* [General Information](#general-information)
* [Installation](#installation)
* [Project status](#project-status)
* [Contact](#Contact)


## General Information
This project contains two parts: a server and a client.

The server can receive 5 types of messages:

1. Registration: The customer sending this message wishes to join the group chat. The message will be in the following format: 1 [Name] When the server receives such a message, it adds the sender to the group. This means that:
* The server saves the client's name and its socket details.
* The server sends the message to all participants in the group: [Name] has joined
* The server sends the joined client the names of the group members.

2. Sending a message: A customer wants to send a message to all members of the group. The message will be in the following format: 2 [Message] When the server receives such a message, it sends the message to all members of the group: [Name]: [Message]

3. Name change: The client sending this message wishes to change his name in the group. The message will be in the following format: 3 [Name] When the server receives this message, it sends the message to all members of the group: [old name] changed his name to [new name]

4. Leaving the group: The customer sending this message wishes to leave the group (and in particular, to stop receiving updates from it). The message will be in the following format: 4 When the server receives this message, it sends the message to all members of the group: [Name] has left the group

5. Receiving new information: The client sending this message requests the server to send him all the messages sent to him since the last update. The message will be in the following format: 5 When the server receives this message, it sends the client back one message containing all the messages that should have been sent to it since the previous time.

If the client sent a message to the server that is not according to what was defined above, the server must ignore the message and return the request: "Illegal message" to the client.

## Installation
Before installing this project, you need to install on your computer:
* Git

After it, run the following commands in the terminal:

```
git clone https://github.com/ShaharMosh/network_ex_1.git
```
Run the server:
```
python server.py port
```
For example: 
```
python server.py 12345
```
Open new terminals for the clients and run the following command:

```
python client.py ip port
```
For example: 
```
python client.py 127.0.0.1 12345
```
## Project status 
The project is in the beginning stages and will develop over time.

## Contact
Created by @adi-ben-yehuda and @ShaharMosh - feel free to contact us!
