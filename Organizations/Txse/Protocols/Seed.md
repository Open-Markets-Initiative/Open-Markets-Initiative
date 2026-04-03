## Seed: Txse Order Entry

Binary order entry protocol for submitting and managing orders on the Texas Stock Exchange.

### Overview

Seed is the Txse binary order entry protocol providing a low-latency interface for trading on the Texas Stock Exchange. The protocol supports order submission, modification, cancellation, and execution reporting using a compact binary encoding designed for efficient processing by both exchange systems and participant applications.

The protocol handles the complete order lifecycle from new order acknowledgment through fill notification, including partial fills, order rejects, cancel confirmations, and replace acknowledgments. Seed is transported over the Rake session layer which provides framing, sequencing, and session management services.

### Transport

Tcp via the Rake session layer. Rake provides message framing, sequence numbering, authentication, and heartbeat management for Seed order entry sessions.

### Key Characteristics

- **Binary encoded** - Compact binary message format for low-latency order entry
- **Full order lifecycle** - New, replace, cancel, fill, and reject messages
- **Rake session layer** - Framing and session management via the Rake protocol
- **Low latency** - Optimized encoding for high-frequency order flow
- **Sequenced delivery** - Ordered message delivery with sequence number tracking
- **Execution reporting** - Real-time fill and acknowledgment notifications
