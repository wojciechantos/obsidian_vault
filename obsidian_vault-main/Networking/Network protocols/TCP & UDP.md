[[Network Protocols]] [[Networking]]

TCP and UDP provide the essential transfer layer foundation for many of the application protocols covered in other examples.

![[tcp_udp.png]]

HTTP and Web Socket are built on top of TCP. They rely on TCPs reliable transmission, ordered data delivery and conjustion control to smoothly exchange the messages and keep real time connection stable. 

The newer HTTP/3 protocol utilizes UDP via the QUIC protocol. This allows to optimize performance by reducing overheap compared to TCP.

### Crucial differences

**TCP** prioritizes reliability over raw speed. Features like:
- error checking
- transmission control
- ordered data delivery
ensure robust performance.

TCP adapts to network conditions with:
- flow control
- retransmissions

**UDP** focuses on speed over reliability with very lightweight error checking and no handshakes. UDP minimizes overheap for use cases like:
- gaming
- voice
- IoT (Internet of Things)
- streaming
UDP data can be corrupted by dropped packets, but combining it with application layer integrity checks ballances speed and reliability.