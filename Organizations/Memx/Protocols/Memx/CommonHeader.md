## Common Header: Memx Shared Packet Header Layer

Shared packet header and framing layer used across all Memx binary protocols to provide session identification, sequence numbering, and message ordering.

### Overview

The Memx Common Header is the shared framing layer used across all binary protocols running on the Memx platform, including Memo order entry, Memoir market data feeds, and the risk control protocol. It defines the packet header fields that appear on every datagram regardless of application protocol.

The header carries session identifier, starting sequence number, message count, and timestamp information so that subscribers and clients can validate packet ordering, detect gaps, and correlate events across the Memx protocol family. By standardising the framing layer, Memx allows clients to share decoder infrastructure and recovery logic across every connection.

### Transport

Udp multicast packet header providing session identifier, sequence number, message count, and timestamp fields for real-time market data feeds. Tcp packet header providing session and sequence framing for gap fill and recovery channels.

### Key Characteristics

- **Shared framing** - Common header across all Memx binary protocols
- **Session identifier** - Per-day session tracking for recovery and correlation
- **Sequence number** - Packet-level sequencing for gap detection
- **Message count** - Number of application messages packed into each datagram
- **Timestamp** - Packet-level timestamp for latency measurement
- **Multi-protocol** - Used by Memo, Memoir feeds, and Risk Control

