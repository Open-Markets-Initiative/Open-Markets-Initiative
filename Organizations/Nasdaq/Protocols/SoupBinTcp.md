## SoupBinTcp: Nasdaq Tcp Session Management

Tcp session management protocol providing login, sequencing, and heartbeat services for Nasdaq order entry and data connections.

### Overview

SoupBinTcp is the Nasdaq session layer protocol for Tcp-based connections including Ouch order entry and Tcp replay feeds. The protocol provides login authentication with username and password, sequenced message delivery with session-scoped sequence numbers, client and server heartbeat messages, and end-of-session notification. SoupTcp is the updated variant with enhanced session management capabilities.

The protocol defines a simple framing format with a two-byte big-endian length prefix followed by a single-byte packet type identifier. Login requests carry credentials and an optional requested sequence number for replay positioning. The server responds with login acceptance including the session identifier and starting sequence number, or login rejection with a reason code. Heartbeat packets maintain connection liveness in both directions.

### Transport

Tcp with length-prefixed binary framing. SoupBinTcp and SoupTcp variants provide the session layer for all Nasdaq Tcp-based protocols including order entry and data replay.

### Key Characteristics

- **Tcp session layer** - Login, sequencing, and heartbeat management
- **SoupBinTcp and SoupTcp** - Original and updated session protocol variants
- **Login authentication** - Username and password credential validation
- **Sequence numbered** - Session-scoped sequence numbers for ordered delivery
- **Bidirectional heartbeat** - Client and server heartbeat packets for liveness
- **Length-prefixed framing** - Two-byte big-endian length prefix per packet
