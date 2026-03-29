## Memo: Boats Binary Order Entry

Sbe-encoded binary order entry protocol for submitting and managing orders on Blue Ocean Ats.

### Overview

Memo is the binary order entry protocol used by Blue Ocean Ats (Boats) for electronic trading of equities during overnight sessions. Built on the Memx technology platform, Memo uses Simple Binary Encoding (Sbe) to provide low-latency, fixed-length message encoding for order submission, modification, and cancellation.

The protocol supports equity order types with various time-in-force options appropriate for overnight trading. Memo provides real-time execution reports and order status updates over persistent Tcp sessions, enabling participants to manage their order flow during extended hours.

### Transport

Tcp with session-level sequencing and heartbeat management. Clients connect to Boats gateways and maintain persistent sessions for order lifecycle management.

### Key Characteristics

- **Sbe encoded** - Fixed-length binary fields for efficient low-latency parsing
- **Memx platform** - Built on proven Memx exchange technology
- **Overnight trading** - Designed for extended hours equities trading
- **Sequenced messaging** - Bidirectional sequence numbers for reliable delivery
- **Real-time execution reports** - Immediate acknowledgments and fill notifications
- **Session management** - Login, heartbeat, and graceful disconnect handling
