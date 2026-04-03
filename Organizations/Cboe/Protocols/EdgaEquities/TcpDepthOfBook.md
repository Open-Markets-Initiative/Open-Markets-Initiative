## Cboe Edga Equities Tcp Depth Of Book

Pitch Tcp feed providing full order-level depth of book for Cboe Edga Equities Exchange over a reliable Tcp connection.

### Overview

Equities Tcp Depth Of Book delivers the same order-by-order market data as the multicast depth of book feed but over a point-to-point Tcp connection. This provides built-in reliable delivery without requiring multicast infrastructure or client-side gap detection and recovery logic.

The feed is suited for participants who cannot receive Udp multicast or prefer the simplicity of Tcp-based data delivery. It includes the full set of order add, modify, cancel, and execution messages for complete book reconstruction.

### Transport

Tcp with sequenced delivery and session-level heartbeat management.

### Key Characteristics

- **Tcp delivery** - Reliable point-to-point connection without multicast requirements
- **Full depth** - Same order-level content as the multicast depth of book feed
- **Built-in recovery** - Tcp handles retransmission without client-side gap management
- **Session management** - Login, heartbeat, and sequence-based reconnection support
