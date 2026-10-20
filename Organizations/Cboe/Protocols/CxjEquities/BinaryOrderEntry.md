## CxjEquities Binary Order Entry: Cboe Japan Binary Order Entry

Cboe Binary Order Entry version 3 (Boe3) protocol for submitting, modifying, cancelling, and purging orders on Cboe Japan equities.

### Overview

Binary Order Entry is the Cboe Boe3 protocol for Cboe Japan (Alpha and Select), providing participants with a binary interface to submit, modify, cancel, and purge orders. Messages are statically sized except for repeating groups, little-endian, and framed by a common message header carrying the message type, matching unit, and sequence number.

Participant messages cover new order, modify order, cancel order, and purge orders; Cboe Japan returns order acknowledgements, rejects, modifications, restatements, executions, cancellations, and purge acknowledgements. The session layer provides login with per-unit replay, heartbeats, and logout.

### Transport

Tcp via the Cboe Binary Order Entry (Boe) session layer for persistent authenticated order flow with sequence tracking, heartbeats, and replay on login.

### Key Characteristics

- **Cboe Boe3** - Native Cboe Binary Order Entry version 3 protocol
- **Full order lifecycle** - New, modify, cancel, purge, and execution report messages
- **Cash and margin orders** - Cash, margin open, and margin close orders with negotiable or standardized margin transactions
- **Self-trade protection** - NoTradeKey and NoTradeFeat instructions with restatement of prevented matches
- **Session based** - Persistent authenticated Tcp session per participant with per-unit replay

