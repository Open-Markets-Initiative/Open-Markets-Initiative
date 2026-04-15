## JnxBonds Ouch: Japannext Pts Bonds Order Entry

Ouch-based binary order entry protocol for submitting, modifying, and cancelling orders on the Japannext Jnx Pts bonds venue.

### Overview

JnxBonds Ouch is the order entry protocol for the Japannext Jnx Pts bonds venue, providing members with a low-latency binary interface to submit, replace, and cancel orders against listed bond instruments. The wire format is a Japannext subset of the Ouch message family with fixed-width binary fields and numeric token references for efficient order management.

Messages are framed with SoupBinTcp over Tcp, providing session authentication, heartbeat monitoring, and sequence-based recovery. Inbound messages include Enter Order, Replace Order, and Cancel Order, and outbound messages report order accepted, replaced, cancelled, and executed events back to the client, sharing the architecture of the JnxEquities Ouch protocol.

### Transport

Tcp via SoupBinTcp for persistent authenticated trading sessions carrying Enter Order, Replace Order, Cancel Order, and execution report messages with sequence-based recovery.

### Key Characteristics

- **Session-based** - Persistent authenticated Tcp session per member
- **Ouch encoded** - Compact fixed-width Ouch-style binary messages
- **SoupBinTcp framed** - Session layer provides heartbeat and sequence recovery
- **Full order lifecycle** - Enter, replace, cancel, accepted, replaced, cancelled, and executed
- **Bonds order entry** - Designed for the Jnx Pts bonds venue

