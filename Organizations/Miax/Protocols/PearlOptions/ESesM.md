## PearlOptions ESes M: Miax Express Session Layer

Session management layer used by Miax binary protocols to establish authenticated sessions, exchange heartbeats, and recover sequence gaps across market data and order entry feeds.

### Overview

ESesM is the Miax Express Session Manager protocol, a shared session layer used across the Miax family of binary market data and order entry protocols. It handles session establishment, authentication, heartbeat monitoring, and sequence-based recovery over Tcp, providing a common framework that application-level feeds such as Top of Market and Express Orders build on.

The session layer defines login and logout message flows, periodic heartbeat exchanges for liveness detection, sequence number negotiation so that clients can resume after a transient disconnect, and gap fill request messages for replay of missing sequence ranges. By consolidating these concerns into a single reusable layer, Miax keeps the application-level protocols focused on their own message content.

### Transport

Tcp session layer carrying login, logout, heartbeat, sequence reset, and gap fill request messages shared across Miax Express market data and order entry interfaces.

### Key Characteristics

- **Shared session layer** - Used across Miax market data and order entry protocols
- **Authentication** - Login and logout handshakes with credential checks
- **Heartbeat** - Periodic keepalive exchanges for liveness detection
- **Sequence recovery** - Sequence number negotiation and gap fill requests
- **Binary encoded** - Compact fixed-width session messages
- **Tcp delivered** - Session state carried over a persistent Tcp connection

