## Pts Bonds Ouch: Jnx Order Entry

Pts Ouch order entry protocol for bonds traded on the Japannext proprietary trading system.

### Overview

Pts Bonds Ouch is the order entry protocol used by Japannext for submitting, modifying, and cancelling bond orders on the Jnx Pts venue. The protocol provides a binary message interface for entering limit and market orders with various time-in-force options for all listed bond instruments.

The protocol carries inbound messages for order entry, replacement, and cancellation, and returns outbound messages including acknowledgements, execution reports, and rejection notifications. Bonds Ouch provides a low-latency order management interface for direct market access participants connecting to the Jnx Pts matching engine.

### Transport

Tcp with session layer providing connection management, sequencing, and heartbeat keepalive.

### Key Characteristics

- **Binary order entry** - Fixed-format binary messages for low-latency order submission
- **Full order lifecycle** - Enter, replace, and cancel with execution reports
- **Bonds focused** - Supports all bond instruments on the Jnx Pts
- **Real-time fills** - Inline acknowledgment and execution messages on the same session
