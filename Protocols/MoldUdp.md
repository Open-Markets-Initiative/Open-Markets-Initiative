## MoldUDP: MoldUDP / MoldUDP64

Nasdaq's UDP-based transport protocol for sequenced, recoverable delivery of market data messages over multicast, serving as the transport layer beneath ITCH market data feeds.

### Overview

MoldUDP is a lightweight transport protocol designed by Nasdaq to deliver sequenced messages over UDP multicast with support for gap detection and retransmission. It provides the framing, sequencing, and session management required for reliable market data delivery without the overhead of TCP connections for each subscriber. MoldUDP64 is the current generation using 64-bit sequence numbers, replacing the original MoldUDP which used 32-bit sequence numbers.

Each MoldUDP64 packet consists of a session identifier, sequence number, and message count, followed by one or more length-prefixed application messages. The session identifier is a 10-byte ASCII string that changes each trading day, scoping the sequence number space to a single session. Sequence numbers are strictly increasing and contiguous, allowing receivers to detect gaps by comparing expected and received sequence numbers.

When a receiver detects a gap, it can request retransmission of specific missed messages by sending a UDP unicast request to a designated retransmission server specifying the session, starting sequence number, and count. MoldUDP64 also defines heartbeat packets (message count of zero) sent during idle periods to confirm the feed is active and to advance the expected sequence number for gap detection. An End of Session packet signals the close of the current session.

### Transport

MoldUDP64 operates over UDP multicast for primary data distribution. Retransmission requests are sent via UDP unicast to a dedicated retransmission server which responds with the requested messages over UDP unicast. Heartbeat packets with a message count of zero are sent during idle periods. The protocol uses big-endian (network byte order) for all numeric fields in the packet header.

### Key Characteristics

- **UDP multicast delivery** - Primary distribution via multicast for efficient one-to-many dissemination
- **64-bit sequence numbers** - Strictly increasing contiguous sequence numbers for gap detection (upgraded from 32-bit in original MoldUDP)
- **Session-scoped** - 10-byte ASCII session identifier changes daily scoping the sequence number space
- **Retransmission service** - UDP unicast request/response for recovery of missed messages
- **Heartbeat packets** - Zero-message-count packets during idle periods confirming feed liveness
- **End of Session** - Explicit session termination packet
- **Length-prefixed messages** - Each application message preceded by a 2-byte length field
- **Big-endian header** - Network byte order for all packet header numeric fields
