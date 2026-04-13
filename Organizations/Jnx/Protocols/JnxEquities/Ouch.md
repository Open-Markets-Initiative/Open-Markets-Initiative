## Pts Equities Ouch: Jnx Order Entry

Pts Ouch order entry protocol for equities traded on the Japannext proprietary trading system.

### Overview

Pts Equities Ouch is the order entry protocol used by Japannext for submitting, modifying, and cancelling equity orders on the Jnx Pts venue. The protocol provides a binary message interface for entering limit and market orders with various time-in-force options for all listed equities.

The protocol carries inbound messages for order entry, replacement, and cancellation, and returns outbound messages including acknowledgements, execution reports, and rejection notifications. Equities Ouch provides a low-latency order management interface for direct market access participants connecting to the Jnx Pts matching engine.

### Transport

Tcp with session layer providing connection management, sequencing, and heartbeat keepalive.

### Key Characteristics

- **Binary order entry** - Fixed-format binary messages for low-latency order submission
- **Full order lifecycle** - Enter, replace, and cancel with execution reports
- **Equities focused** - Supports all equity instruments on the Jnx Pts
- **Real-time fills** - Inline acknowledgment and execution messages on the same session
