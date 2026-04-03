## Memo: 24X Binary Order Entry

Sbe-encoded binary order entry protocol for submitting and managing orders on the 24X National Securities Exchange.

### Overview

Memo is the binary order entry protocol used by 24X for electronic trading of equities. Built on the Memx technology platform, Memo uses Simple Binary Encoding (Sbe) to provide low-latency, fixed-length message encoding for order submission, modification, and cancellation.

The protocol supports standard equity order types including limit, market, and pegged orders with various time-in-force options. Memo provides real-time execution reports and order status updates over persistent Tcp sessions.

### Transport

Tcp with session-level sequencing and heartbeat management. Clients connect to 24X gateways and maintain persistent sessions for order lifecycle management.

### Key Characteristics

- **Sbe encoded** - Fixed-length binary fields for efficient low-latency parsing
- **Memx platform** - Built on proven Memx exchange technology
- **Sequenced messaging** - Bidirectional sequence numbers for reliable delivery
- **Real-time execution reports** - Immediate acknowledgments and fill notifications
- **Session management** - Login, heartbeat, and graceful disconnect handling
