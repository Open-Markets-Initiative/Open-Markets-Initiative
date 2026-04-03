## Common Header: Memx Session Headers

Transport-level header protocol defining Tcp and Udp session framing for all Memx protocols.

### Overview

The Memx Common Header protocol defines the session-level framing and header structure used across all Memx binary protocols. It provides a unified header format for both Tcp order entry connections and Udp multicast market data feeds, establishing consistent message boundaries, sequencing, and session identification.

The header framework supports login and logout handshakes for Tcp sessions, heartbeat messages for connection monitoring, and sequence number management for ordered message delivery. For Udp multicast feeds, the common header provides packet-level framing with sequence numbers for gap detection and message count fields for demarcating individual messages within multicast packets.

### Transport

Tcp for order entry session framing and Udp for multicast market data packet framing. The common header is the outermost layer wrapping all Memx Sbe-encoded business messages.

### Key Characteristics

- **Dual transport** - Header variants for both Tcp and Udp protocols
- **Session management** - Login, logout, and heartbeat for Tcp connections
- **Sequence numbering** - Ordered delivery tracking for both Tcp and Udp
- **Message framing** - Length-prefixed message boundaries within packets
- **Unified format** - Consistent header structure across all Memx protocols
- **Gap detection** - Sequence number tracking for identifying missed messages
