## SoupBinTcp: Nasdaq point-to-point sequenced TCP session layer

Lightweight point-to-point protocol on top of TCP/IP sockets that delivers a set of sequenced messages from a server to a client in real time, guaranteeing in-sequence receipt even across socket connection failures.

### Overview

Each SoupBinTCP logical packet has a two byte big-endian length of the rest of the packet, a single byte packet type and a variable length payload. Logical packets need not map to physical packets on the socket, and the payload may contain any byte, unlike the ASCII SoupTCP from which SoupBinTCP 3.0 was taken. SoupBinTCP is opaque to the higher level messages it carries.

The client sends a Login Request with username, password, requested session and requested sequence number; the server answers Login Accepted with the session and next sequence number, or Login Rejected. Sequenced Data Packets carry one higher level message each and no explicit sequence number: both sides count them, starting at 1 in each session. After a socket failure the client logs in again with its session and next expected sequence number. Server and client each send a heartbeat when more than one second passes without sending anything, and the server ends a session with an End of Session Packet. Debug Packets may be sent by either side and are ignored.

SoupBinTCP 4.00 added unsequenced data packets from the server to the client, which clients must not count when computing the sequence number, and 4.1 added a heartbeat timeout field to the login request.

### Transport

TCP/IP socket opened by the client, which logs in and then receives Sequenced Data Packets; the client may send Unsequenced Data Packets, which may be lost on a socket failure.

### Key Characteristics

- **Length-prefixed packets** - Two byte big-endian length, one byte packet type, variable payload
- **Login authentication** - Username and password login selecting the session and next sequence number
- **Implicit sequence numbers** - Sequenced Data Packets are counted by both sides from 1 in each session
- **Recovery by re-login** - After a socket failure the client re-logs in at its next expected sequence number
- **Heartbeats both ways** - Server and client heartbeats after more than one second without data
- **End of Session** - Explicit End of Session Packet closes the current session

