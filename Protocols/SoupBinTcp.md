## SoupBinTCP: SoupBinTCP / SoupTCP

Nasdaq's TCP-based session layer protocol providing login, heartbeat, sequencing, and message delivery for point-to-point connections, serving as the session layer beneath OUCH order entry and other Nasdaq protocols.

### Overview

SoupBinTCP is a lightweight point-to-point session protocol designed by Nasdaq to provide reliable framed message delivery over TCP connections. It handles session establishment, authentication, sequencing, heartbeat monitoring, and message recovery, allowing application protocols such as OUCH to focus on business logic without implementing their own session management. SoupBinTCP is the binary successor to the original SoupTCP protocol which used text-based framing.

Each SoupBinTCP session begins with a Login Request from the client specifying credentials, a requested session identifier, and a requested sequence number. The server responds with a Login Accepted (including the actual session and sequence number) or Login Rejected message. Once established, the server sends sequenced data messages with implicit sequence numbers that increment with each message. The client sends unsequenced data messages for order entry which do not carry sequence numbers.

The protocol includes bidirectional heartbeat messages sent when no other data has been transmitted within a configurable interval. Either side can detect a dead connection by monitoring for the absence of any traffic. End of Session messages signal that the server will not send any more data on the current session. Upon reconnection, clients specify the last received sequence number to resume from where they left off, enabling automatic gap recovery.

### Transport

SoupBinTCP operates over TCP providing reliable ordered delivery. Each message is framed with a 2-byte big-endian packet length followed by a 1-byte packet type identifier and the message payload. The protocol is designed for point-to-point connections between a single client and server. All numeric fields in the session layer use big-endian (network byte order).

### Key Characteristics

- **TCP session layer** - Lightweight framing and session management over TCP for point-to-point connections
- **Login and authentication** - Session establishment with credentials, session identifier, and sequence number negotiation
- **Implicit sequencing** - Server-to-client messages carry implicit incrementing sequence numbers for gap recovery
- **Heartbeat monitoring** - Bidirectional heartbeats detect dead connections during idle periods
- **Session resumption** - Clients reconnect specifying last received sequence number to resume delivery
- **End of Session** - Explicit session termination signaling no more data will be sent
- **Length-prefixed framing** - 2-byte big-endian packet length followed by packet type and payload
- **Binary successor** - SoupBinTCP replaced the older text-based SoupTCP protocol
