[[Network Protocols]] [[Networking]]

It is built on top of HTTP protocol by adding encryption through TLS (Transport Layer Security)

![[https.png]]

The HTTP request does not go directly to the server. There are intermediaries like internet service provider or when we work on a public WiFi in a coffee shop. So it basically means that the service provider you used to send a request has access and can see the data you passed within a request, because all the passed data is in plain text format. Here is where a HTTPS encryption comes into play.

TLS allows to browser and server to establish an encrypted connection like two people agreeing on a secret code. This encrypted connection keeps the data confidential as it travels over the public internet. Traffic is scrambled, so it is meaningless to anyone intercepting it. TLS also verifies a servers identity to prevent from the so called "man in the middle attack". 

TLS provides encryption, security and authentication that powers HTTPS in secure websites. Understanding it is important for safety which is critical for sectors like banking or e-commerce.