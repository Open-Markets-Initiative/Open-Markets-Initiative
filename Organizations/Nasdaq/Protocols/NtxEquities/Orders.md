## NtxEquities Orders: Nasdaq BX Order Entry

Ouch-based binary order entry protocol for submitting, replacing, and cancelling orders on Nasdaq BX Equities.

### Overview

Orders is the Nasdaq Ouch order entry protocol variant for Nasdaq BX Equities, providing members with a low-latency binary interface to submit, replace, and cancel orders for equities. The wire format is the Ouch message family with fixed-width binary fields and numeric token references for efficient order management.

Messages are framed with SoupBinTcp over Tcp which provides session authentication, heartbeat monitoring, and sequence-based recovery. Inbound messages include Enter Order, Replace Order, Cancel Order, and Cancel By Order Id, and outbound messages report order accepted, replaced, cancelled, and executed events.

### Transport

Tcp via SoupBinTcp for persistent authenticated Ouch sessions carrying order submission, replacement, cancellation, and execution report messages.

### Key Characteristics

- **Nasdaq Ouch** - Industry-standard Ouch order entry protocol
- **SoupBinTcp framed** - Session-authenticated Tcp with heartbeat and sequence recovery
- **Full order lifecycle** - Enter, replace, cancel, accepted, replaced, cancelled, and executed
- **Session based** - Persistent authenticated Tcp session per member
- **Binary encoded** - Fixed-width Ouch binary messages for low latency

