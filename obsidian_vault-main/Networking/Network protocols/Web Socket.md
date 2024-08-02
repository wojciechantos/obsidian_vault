[[Network Protocols]] [[Networking]]

Unlike HTTP, Web Socket provides full duplex bi-directional communication on a single TCP connection.

![[webSocket 1.png]]

Web Socket enables seamless real-time collaboration and live data streams. The initial Web Socket "handshake" reuses the existing TCP connection. The messages can flow freely in both directions with minimal framing.

![[webSocketConnection.png]]

Web Socket supports sending small messages with very low over-heap ideal for chat, gaming or real-time updates while encryption via TLS is supported for security.

![[webSocketSecurity.png]]

