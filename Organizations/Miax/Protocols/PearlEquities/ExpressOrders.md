## Pearl Equities Express Orders: Meo Order Entry

Meo express order entry protocol for Miax Pearl Equities exchange.

### Overview

Pearl Equities ExpressOrders is the Meo order entry protocol providing a low-latency binary interface for trading on the Miax Pearl Equities exchange. The protocol delivers optimized order submission, modification, and cancellation capabilities using compact binary encoding over Tcp, targeting high-frequency and latency-sensitive order flow.

Express Orders are designed for minimal processing overhead, providing a streamlined message set focused on rapid order entry and execution reporting. The protocol supports standard order types and time-in-force instructions for equity instruments on Pearl Equities with inline acknowledgment and execution messages.

### Transport

Tcp to Miax Pearl Equities matching engine gateways with sequenced message delivery and heartbeat monitoring.

### Key Characteristics

- **Express orders** - Optimized message set for minimal processing overhead
- **Binary Tcp** - Compact binary encoding for low-latency order entry
- **Full order lifecycle** - New, replace, cancel, fill, and reject messages
- **Low latency** - Streamlined protocol designed for high-frequency trading
