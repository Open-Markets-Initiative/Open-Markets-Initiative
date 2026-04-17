## CoinbaseDerivatives Session: Coinbase Derivatives Sbe Session Layer

Binary session layer protocol handling connection lifecycle, authentication, and heartbeat for Coinbase Derivatives market data and order entry interfaces.

### Overview

Coinbase Derivatives Session is the shared Sbe-encoded session layer protocol that underpins both the market data api and the orders api. It handles session lifecycle events including credential-based authentication at login, sequence number negotiation, heartbeat-monitored liveness detection, and graceful termination, providing a common foundation for application-level messaging across Coinbase Derivatives interfaces.

The session layer supports gap detection and reconnection through sequence number tracking, so that clients can resume after a transient disconnect without losing state. Session messages use the same Sbe encoding as the application protocols they serve, which keeps the wire format uniform and allows clients to share decoder infrastructure across the full Coinbase Derivatives stack.

### Transport

Tcp for session lifecycle messages including negotiate, establish, heartbeat, and terminate, providing a common authenticated delivery path for application layer protocols.

### Key Characteristics

- **Sbe encoded** - Simple Binary Encoding consistent with application layer protocols
- **Authentication** - Credential-based login for secure session establishment
- **Heartbeat monitoring** - Periodic keepalive exchanges to detect connection failures
- **Sequence synchronization** - Sequence number management for message recovery
- **Shared layer** - Common foundation for market data and order entry interfaces
- **Graceful termination** - Orderly logout and session teardown procedures
- **Reconnection** - Session resume via sequence number negotiation after transient disconnects

