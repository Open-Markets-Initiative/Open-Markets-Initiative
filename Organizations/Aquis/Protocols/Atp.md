## Atp: Aquis Trading Protocol

Binary order entry protocol for submitting and managing orders on the Aquis Exchange.

### Overview

Atp is the native binary order entry protocol for Aquis Exchange, providing electronic trading access for equities across Aquis European venues. The protocol supports order submission, modification, cancellation, and execution reporting with binary-encoded messages for efficient low-latency communication.

Atp provides a full order lifecycle management interface including support for various order types, time-in-force options, and execution instructions. The protocol handles session management with login, heartbeat, and sequencing to maintain reliable connectivity to Aquis matching engines.

### Transport

Tcp to Aquis trading gateways. Sessions are established with authentication and maintained with heartbeat monitoring and bidirectional sequence number tracking.

### Key Characteristics

- **Binary encoded** - Efficient binary message format for low-latency order handling
- **Full order lifecycle** - New order, modify, cancel, and execution report messages
- **Session management** - Login, heartbeat, and sequence number synchronization
- **Multiple order types** - Limit, market, and pegged order support
- **Real-time execution reports** - Immediate acknowledgments and fill notifications
