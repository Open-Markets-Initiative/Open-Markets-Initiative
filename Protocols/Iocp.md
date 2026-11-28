## Iocp: Internet Oriented Communication Portal

Binary control protocol of the Athens Exchange Feed Information Center Tcp service, through which a data vendor authenticates and starts, stops and recovers the Ids market data feed of the Oasis trading system.

### Overview

The Iocp separates control from data: the vendor interacts with the service only through the control channel, and the data channel is one-way, carrying the Ids market data messages. Control messages authenticate the vendor through a SHA1 hash challenge and response, check and close channels, and begin or stop transmission and retransmission of the feed.

Every control message opens with two characters naming it, and no message carries a length: each has a fixed width. Multi-byte numbers are little endian.

### Transport

A control channel the vendor opens first, followed by one data channel matching its account type, time-sensitive or relaxed, which carries the Ids feed.

### Key Characteristics

- **Separate control and data channels** - Requests and replies on the control channel, the Ids feed on the data channel
- **Challenge response authentication** - A random number from the server is hashed with the vendor's credentials and IP address
- **Two character message types** - Fixed width messages named by two leading characters, with no length field
- **Little endian** - Multi-byte integers are little endian

