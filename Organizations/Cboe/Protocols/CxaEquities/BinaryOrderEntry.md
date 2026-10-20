## CxaEquities Binary Order Entry: Cboe Australia Binary Order Entry

Cboe Binary Order Entry version 3 (Boe3) protocol for submitting, modifying, cancelling, and purging orders on Cboe Australia equities.

### Overview

Binary Order Entry is the Cboe Boe3 protocol for Cboe Australia, providing participants with a binary interface to submit, modify, cancel, and purge orders. Messages are statically sized except for repeating groups, little-endian, and framed by a common message header carrying the message type, matching unit, and sequence number.

Participant messages cover new order and modify order (V1 and V2), cancel order, and purge orders; Cboe Australia returns acknowledgements, rejects, modifications, restatements, executions, execution restatements, trade cancels, carried restatements and done for day messages for multi-day orders, and purge acknowledgements. The session layer provides login with per-unit replay, heartbeats, and logout.

### Transport

Tcp via the Cboe Binary Order Entry (Boe) session layer for persistent authenticated order flow with sequence tracking, heartbeats, and replay on login.

### Key Characteristics

- **Cboe Boe3** - Native Cboe Binary Order Entry version 3 protocol
- **Full order lifecycle** - New, modify, cancel, purge, and execution report messages
- **Market Integrity Rules** - Origin of order, intermediary, and directed wholesale fields on every order
- **Multi-day orders** - GTC and GTD orders with carried restatement and done for day messages
- **Session based** - Persistent authenticated Tcp session per participant with per-unit replay

