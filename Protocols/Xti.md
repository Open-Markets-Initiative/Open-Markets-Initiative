## Xti: Eurex T7 Order Entry

Binary order entry interface for the Eurex T7 trading platform supporting order and quote submission for the cash market.

ETI is Eurex's binary order entry protocol on T7, used by trading participants for the full order lifecycle across cash market products on T7.

### Overview

Eti is the Eurex Enhanced Trading Interface, a binary session-based order entry protocol for the Eurex T7 trading platform. It is used by participants to submit, modify, and cancel orders and quotes across Eurex products including derivatives and cash markets hosted on the T7 infrastructure. The wire format is a compact fixed-width binary encoding tailored for low latency.

The protocol defines session negotiation and logon handshakes, sequence number tracking for reliable delivery, recovery of unacknowledged messages after reconnection, and a rich set of application messages covering new orders, order modifications, mass quote submissions, execution reports, and trade captures. It is the primary order entry interface for listed derivatives across Eurex and the other markets running on the T7 platform.

### Transport

Tcp for persistent authenticated sessions carrying order submission, modification, cancellation, quote entry, and execution report messages with sequence-numbered reliable delivery.

### Key Characteristics

- **T7 platform** - Native interface for the Eurex T7 trading system
- **Order and quote entry** - Full message set for orders, quotes, and mass quotes
- **Binary encoded** - Fixed-width compact binary messages for low latency
- **Session based** - Persistent authenticated Tcp sessions with sequence tracking
- **Reliable delivery** - Retransmission of unacknowledged messages after reconnection
- **Derivatives and cash** - Unified order entry across Eurex asset classes on T7

