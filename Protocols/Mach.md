## Mach: MIAX MACH Protocol

MIAX's proprietary binary multicast protocol used for real-time market data dissemination across all MIAX exchange platforms, including MIAX Options, MIAX Pearl Options, MIAX Pearl Equities, MIAX Emerald, and MIAX Sapphire.

### Overview

MACH is a scalable and lightweight multicast-based protocol that allows a publisher to transmit market data to many subscribers simultaneously. It serves as the underlying transport layer for MIAX's proprietary data feeds, including Top of Market (ToM), Complex Top of Market (cToM), Liquidity Feeds, and Depth of Market feeds. MACH defines the handling of multicast transmissions from the exchange, providing session-level communication and a packet structure that enables subscribers to detect and manage gaps in the data stream.

Each MACH channel is assigned a unique multicast group and/or port. MACH packets contain a unique sequence number, and one or more application messages may be buffered into a single UDP packet for efficient transmission. The protocol does not provide delivery guarantees; when a subscriber detects a gap in sequence numbers, publisher-side applications typically offer a separate retransmission service or redundant feeds for recovery. For redundancy, subscribers may connect to two identical feeds (an A feed and a B feed) for each matching engine.

A MACH session begins when the publisher sends a Start of Session packet and ends with an End of Session packet. The publisher sends heartbeat packets whenever more than one second passes without data. If a subscriber does not receive any data or heartbeats for an extended period the link or publisher may be considered down.

### Transport

MACH operates over UDP multicast. Market data is disseminated as unidirectional multicast traffic from the exchange publisher to subscribers. The protocol limits the maximum payload length to 65,535 bytes minus the header size. Gap recovery is handled outside the MACH protocol layer, typically through a separate TCP-based retransmission service or by arbitrating between redundant A/B multicast feeds.

### Key Characteristics

- **Binary multicast** - Lightweight binary packet format transmitted over UDP multicast for high-throughput delivery
- **Sequenced packets** - Each packet carries a unique sequence number within a session enabling gap detection
- **Session management** - Sessions bounded by Start of Session and End of Session packets with assigned session numbers
- **Heartbeat monitoring** - Publisher sends heartbeats at least every second during idle periods for link failure detection
- **Redundant feeds** - Subscribers can connect to dual A/B feeds per matching engine for failover
- **No delivery guarantee** - Gap recovery is delegated to application-level retransmission services or feed arbitration
- **Multi-exchange** - Same protocol specification used across all MIAX exchange platforms

