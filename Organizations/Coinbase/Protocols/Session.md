## Session: Coinbase Session Management

Binary session management protocol for establishing and maintaining authenticated connections to Coinbase exchange services using Sbe encoding.

### Overview

Session is Coinbase's binary session layer protocol handling connection lifecycle management for the MarketDataApi and OrdersApi interfaces. The protocol manages authentication, session establishment, heartbeat monitoring, and graceful disconnection using Sbe-encoded messages consistent with the application-layer protocols it supports.

The session layer provides a common foundation for both market data and order entry connectivity. It handles credential-based authentication during login, maintains session liveness through periodic heartbeat exchanges, and supports sequence number synchronization for message recovery after reconnection. The protocol ensures that application-layer messages are delivered within a properly authenticated and monitored session context.

### Transport

Tcp connections to Coinbase gateways. The Session protocol operates as the initial handshake and ongoing maintenance layer over the same Tcp connection used by MarketDataApi or OrdersApi application messages.

### Key Characteristics

- **Sbe encoded** - Fixed-position binary fields consistent with application-layer protocols
- **Authentication** - Credential-based login for secure session establishment
- **Heartbeat monitoring** - Periodic keepalive exchanges to detect connection failures
- **Sequence synchronization** - Sequence number management for message recovery
- **Shared session layer** - Common foundation for both market data and order entry interfaces
- **Graceful termination** - Orderly logout and session teardown procedures
