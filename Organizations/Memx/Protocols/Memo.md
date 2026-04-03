## Memo: Memx Order Entry

Sbe-encoded binary order entry protocol for submitting and managing orders on Memx equities and options markets.

### Overview

Memo is the Memx order entry protocol for trading equities and options on the Members Exchange. It provides a low-latency binary interface using Simple Binary Encoding (Sbe) for order submission, modification, cancellation, and execution reporting. The protocol supports a full range of order types and time-in-force instructions for both equity and options instruments.

The protocol delivers deterministic message layouts with fixed-position fields, enabling efficient zero-copy parsing at the client. Memo handles the complete order lifecycle from new order submission through fill notification, including partial fills, order rejects, cancel confirmations, and replace acknowledgments. Risk checks are applied inline during order processing.

### Transport

Tcp to Memx matching engine gateways. Sessions are established using the Memx common header framework with sequenced message delivery and heartbeat-based keepalive.

### Key Characteristics

- **Sbe encoded** - Fixed-position, fixed-length fields for zero-copy parsing
- **Equities and options** - Unified order entry for both asset classes
- **Full order lifecycle** - New, replace, cancel, fill, and reject messages
- **Low latency** - Optimized binary encoding for high-frequency order flow
- **Inline risk checks** - Pre-trade risk validation applied during order processing
- **Sequenced delivery** - Ordered message delivery with sequence number tracking
