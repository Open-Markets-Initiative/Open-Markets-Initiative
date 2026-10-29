## Mold Udp64: Nasdaq one-to-many UDP transport with 64-bit sequence numbers

Lightweight protocol layer on top of UDP for one-transmitter-to-many-listeners delivery, letting listeners detect and re-request missed packets; the 64-bit successor of MoldUDP.

### Overview

MoldUDP64 (version 1.00) transmits each downstream packet only once regardless of the number of listeners, and may aggregate several messages into one packet. Each downstream packet has a 20-byte header: a 10-byte alphanumeric Session, an 8-byte Sequence Number of the first message and a 2-byte Message Count, followed by Message Blocks of a 2-byte Message Length and the message data, whose contents are defined by the higher level application. All number fields are big endian.

A Message Count of zero is a heartbeat, typically sent once per second carrying the next expected sequence number, and a Message Count of 0xFFFF marks the end of the session. A listener that detects a sequence number gap sends a Request Packet (session, first requested sequence number and requested message count) to a Re-request Server, which answers with a standard Downstream Packet by UDP unicast. Optional caching Re-request Servers can be placed near remote receivers to reduce latency and bandwidth over WAN links.

### Transport

Downstream packets via UDP multicast on a well known multicast group per data stream, also sent via UDP unicast in response to a Request Packet submitted to a Re-request Server.

### Key Characteristics

- **Packet framing** - 10-byte session, 8-byte sequence number and 2-byte message count header
- **Message block** - Zero or more length-prefixed application messages per packet
- **Gap detection** - Sequence numbers let listeners detect gaps and re-request them
- **Heartbeat and end of session** - Message Count 0 is a heartbeat, 0xFFFF marks end of session
- **Big endian** - Sequence numbers, counts and lengths are most significant byte first
- **Udp multicast** - Each packet sent once regardless of the number of listeners

