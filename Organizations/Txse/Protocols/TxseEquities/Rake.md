## TxseEquities Rake: Txse Session And Framing Layer

Transport protocol providing session management and message framing for Txse order entry and market data protocols with Tcp and Udp variants.

### Overview

Rake is the Txse session and framing protocol that provides the transport layer for both Seed order entry and Feed market data. The protocol defines message boundaries, sequence numbering, and session lifecycle management, serving as the common transport foundation across all Txse binary protocols. Rake supports both Tcp and Udp transport variants.

The Tcp variant provides connection-oriented session management including login authentication, heartbeat monitoring, sequence synchronization, and graceful session termination for order entry connections. The Udp variant provides packet-level framing with sequence numbers and message counts for multicast market data delivery, enabling gap detection and retransmission requests.

### Transport

Tcp for order entry sessions with connection management, authentication, and bidirectional heartbeat. Udp for multicast market data with sequenced packet framing and gap detection support.

### Key Characteristics

- **Dual transport** - Tcp and Udp variants for order entry and market data respectively
- **Message framing** - Length-prefixed message boundaries within packets
- **Sequence numbering** - Ordered delivery tracking for both Tcp and Udp
- **Session management** - Login, logout, and heartbeat for Tcp connections
- **Gap detection** - Sequence number tracking for identifying missed messages
- **Unified layer** - Common transport foundation for Seed and Feed protocols

