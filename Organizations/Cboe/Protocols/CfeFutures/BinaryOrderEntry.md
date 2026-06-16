## CfeFutures Binary Order Entry: Cboe Futures Binary Order Entry

Cboe Binary Order Entry (Boe) protocol for submitting, modifying, and cancelling orders on Cboe Futures Exchange (CFE).

### Overview

Order Entry is the Cboe Binary Order Entry (Boe) protocol for Cboe Futures Exchange (CFE), providing members with a low-latency binary interface to submit, modify, and cancel orders. The wire format uses compact fixed-width binary messages and a custom session layer with authentication, sequence tracking, and heartbeat monitoring.

The protocol supports the full order lifecycle including new order submission, order modification, cancellation, mass cancellation, execution reports, and cancel rejects. Risk checks are applied inline before orders reach the matching engine, and the session layer provides reliable recovery after transient disconnects.

### Transport

Tcp via the Cboe Binary Order Entry (Boe) session layer for persistent authenticated order flow with sequence tracking, heartbeats, and reliable recovery.

### Key Characteristics

- **Cboe Boe** - Native Cboe Binary Order Entry protocol
- **Full order lifecycle** - New, modify, cancel, mass cancel, and execution report messages
- **Inline risk checks** - Pre-trade risk validation applied during order processing
- **Session based** - Persistent authenticated Tcp session per member
- **Sequence recovery** - Reliable recovery after transient disconnects
- **Low latency** - Compact binary messages for high-frequency order flow

