## ESesM: Extended Session Management

Extended Tcp session management protocol for Miax equities connections.

### Overview

ESesM is the Miax Extended Session Management protocol providing connection lifecycle management for Tcp-based equities trading sessions. The protocol handles session establishment, authentication, heartbeat monitoring, sequence synchronization, and graceful session termination for Miax Pearl Equities order entry connections.

The protocol extends basic Tcp session management with enhanced capabilities for session recovery, sequence number negotiation, and connection state management. ESesM supports reconnection workflows that allow clients to resume sessions and resynchronize sequence numbers after network interruptions, reducing the operational impact of transient connectivity issues.

### Transport

Tcp session layer wrapping Miax equities order entry protocols. ESesM messages frame the outer session while business messages are carried as inner payloads.

### Key Characteristics

- **Extended session management** - Enhanced session lifecycle beyond basic Tcp
- **Authentication** - Session-level credential validation during establishment
- **Heartbeat monitoring** - Bidirectional keepalive for connection health
- **Sequence synchronization** - Sequence number negotiation on connect and reconnect
- **Session recovery** - Reconnection with state resynchronization after interruption
