## BinaryPacket: UMDF UDP packet framing

B3's UDP packet header that wraps each Unified Market Data Feed (UMDF) multicast datagram, carrying per-packet sequence, channel identifier, and timing metadata so subscribers can detect gaps and recover across the B3 equities, derivatives, and fixed income market data channels.

### Overview

B3's Unified Market Data Feed (UMDF) delivers full-depth and summary market data for equities, derivatives, and fixed income products over UDP multicast. Each datagram begins with the BinaryPacket header so subscribers can sequence and time-stamp messages without decoding the SBE payload. The header scopes its sequence number per multicast channel, allowing subscribers to track gaps independently across the many UMDF channels they join.

Each header carries the packet length covering the entire datagram, a channel identifier that names the logical feed, a monotonically increasing packet sequence number unique within the channel, and transmit-time metadata set by the B3 dissemination layer. When gaps are detected, subscribers request retransmission from B3's dedicated gap-recovery service or snapshot service depending on the recovery strategy for the channel.

BinaryPacket is reused across UMDF incremental feeds, snapshot feeds, and instrument definition channels, providing a single framing shape that consumers decode once and reuse for every UMDF subscription. The header is independent of the SBE schemas carried above it, which evolve across UMDF revisions without requiring changes to the framing parser.

### Transport

BinaryPacket sits at the start of every UMDF multicast datagram and carries the packet length, channel identifier, packet sequence number, and packet-level timing fields. The remainder of the datagram holds one or more SBE-encoded application messages following B3's UMDF schemas, each self-describing via its own SBE size and template identifiers.

### Key Characteristics

- **UDP multicast framing** - Wraps every UMDF multicast datagram with sequence and channel metadata
- **Per-channel sequence** - Monotonically increasing packet sequence number scoped to each multicast channel
- **Channel identifier** - Names the logical UMDF feed the packet belongs to
- **Packet timing** - Transmit-time metadata supports latency measurement and cross-channel ordering
- **Multi-message datagrams** - Single packet may carry multiple SBE application messages
- **Schema-independent** - Framing layer is decoupled from the SBE schemas evolving above it
- **Cross-feed reuse** - Shared across UMDF incremental, snapshot, and instrument definition channels
- **Recovery aware** - Sequence gaps drive retransmission or snapshot-replay recovery flows

