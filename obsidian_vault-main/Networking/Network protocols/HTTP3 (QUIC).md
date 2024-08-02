[[Network Protocols]] [[Networking]]

HTTP/3 aims to improve speed and security and fix some nagging performance issues with previous versions.

![[http3.png]]

It uses QUIC built on UDP rather than TCP. This optimizes performance without TCP overheap. It minimizes lag when switching networks on a smartfone.

QUIC brings encryption by default at a transport layer. ALL connection data is encrypted, not just the application payload. Even metadata like packet numbers get scrambled.