
2024-07-30 | 15:27

##### Tags: [[Networking]] 

---

The fundamental concept of the web communication is the Client-Server relation. In practice it simply means that there are always two actors which are:
- **Client** - it is a computer that is making a request to the server
- **Server** - it is a computer that retrieves the request from the client, processes it, and responds adequately

It also important, that the actor that was a server in the initial communication flow also can become a client because for example it's gonna need to make some additional request/s to other instances to collect some data and prepare response for the initial client.

Example (YouTube):
1. Web Browser (client) asks for a certain video by sending a request. 
2. YouTube server that serves the videos retrieves a request from the client, but it does not store any comments, so it needs to send a request to another YT server. It then becomes a client, sends a request, and the comments server responds to it.
3. The YT video server collects the data (video & comments), prepares a response payload and responds to the web browser.

![[Client-Server communication.png]]