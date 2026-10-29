## MoldUdp: Nasdaq Reliable Multicast Transport Layer (original, 32-bit sequence numbers)

Lightweight protocol layer on top of UDP for one-transmitter-to-many-listeners delivery, letting listeners detect and re-request missed packets; the predecessor of MoldUDP64.

### Overview

MoldUDP (version 1.02a, October 2006) is the original Nasdaq reliable multicast transport. Each downstream packet has a 16-byte header: a 10-byte alpha Session, a 4-byte Sequence Number of the first message and a 2-byte Message Count, followed by Message Blocks of a 2-byte Message Length and the message data. All numbers are little endian. A Message Length of zero terminates the session, and a packet with a Message Count of zero is a heartbeat. MoldUDP64 supersedes it with 8-byte sequence numbers and big-endian numbers.

### Transport

Downstream packets via UDP multicast, also sent via UDP unicast in response to a Request message submitted to a Re-request Server.

### Key Characteristics

- **Packet framing** - 10-byte session, 4-byte sequence number and 2-byte message count header
- **Message block** - One or more application messages per datagram
- **Gap detection** - Sequence numbers let listeners detect gaps and re-request them
- **Little endian** - Sequence numbers, counts and lengths are least significant byte first
- **Udp multicast** - Efficient one-to-many delivery

