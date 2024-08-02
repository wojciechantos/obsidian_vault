[[Network Protocols]] [[Networking]]

HTTP - Hyper Text Transfer Protocol

### What is HTTP Protocol?
HTTP protocol is an application-level protocol responsible for communication between clients (such as web browsers) and serves on the World Wide Web (WWW). HTTP defines the format and rules for how clients request resources from servers and how servers respond to those requests. HTTP forms the basis for many web-related technologies and is used for various purposes, including retrieving web pages, uploading files, sending API requests, and many more.

HTTP operates at the app layer of the TCP/IP protocol stack. The TCP/IP stack is a conceptual model that describes the communication protocols used on the Internet. It consists of multiple layers, each responsible for different aspects of data transmission and network communication.

Specifically, HTTP uses TCP (Transmission Control Protocol) as its transport layer protocol. TCP provides reliable, connection-oriented communication between devices over an IP network. It ensures that data packets are delivered in the correct order, without loss, duplication, or errors.

![[HTTPmodel.png]]

Server sends back responses with status codes like:

![[StatusCodes.png]]

The requested data return is retrieved in a response body: 

![[response body.png]]

HTTP defines methods like:

![[httpMethods.png]]

The HTTP request does not go directly to the server. There are intermediaries like internet service provider or when we work on a public WiFi in a coffee shop. So it basically means that the service provider you used to send a request has access and can see the data you passed within a request, because all the passed data is in plain text format. 