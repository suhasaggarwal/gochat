gochat
======

A backend chat server in Go.

Gochat is a backend chat server which uses Redis as a database and messaging 
backend (github.com/simonz05/godis/redis as go-based client) and websockets as 
the primary form of send/receive message routing.

Structure
=========

There are two main parts of Gochat:

- Server: This interface provides the management functions of Gochat such as 
  creating areas, joining areas, listing users and areas, etc.
- Stream Service: This interface provides the methods to start websockets and 
  connect them to Redis pub/sub channels for sending and receiving messages for 
  a particular user and chat area.

To use Gochat for your server, simply make the calls to Server that you require.  
For joining areas, make sure to call Server.JoinArea() AND 
StreamService.InitiateStream().
