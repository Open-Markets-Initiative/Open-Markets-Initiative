## PillarStream: NYSE Pillar Binary Order Entry

Proprietary binary order entry protocol for the NYSE Pillar Gateway, providing a single TCP stream for order submission, modification, cancellation, and execution reporting across all NYSE Group equities and options exchanges.

### Overview

Pillar Stream is the NYSE Pillar Gateway's binary order entry protocol, replacing the legacy CCG and UTPDirect gateways that had evolved independently across the NYSE family of exchanges. It exposes a single standardised stream for member firms to submit orders and receive execution reports across NYSE, NYSE Arca, NYSE American, NYSE National, and NYSE Chicago.

Messages are encoded in a fixed-length little-endian binary format optimised for parse latency. The protocol supports the full order lifecycle including new orders, modifications, cancellations, mass cancels, reserve and hidden order types, complex multi-leg options orders, and detailed execution reports including partial fills, cancel confirmations, and rejections.

The Pillar Stream session layer correlates directly with Pillar market data: OrderIDs and DealIDs assigned on the order-entry side appear verbatim in the Pillar Integrated Feed so participants can reconcile activity without identifier translation. The gateway also enforces built-in pre-trade risk controls including price collars, order size limits, and kill switches.

### Transport

Pillar Stream operates over TCP, providing reliable ordered delivery for the full bidirectional order entry session. Each session covers login, heartbeat, inbound order instructions, and outbound execution reports. The session layer handles sequencing and replay so that the application layer can focus on order-handling semantics.

### Key Characteristics

- **Binary order entry** - Fixed-length little-endian binary format optimised for low-latency submission
- **TCP session** - Single reliable bidirectional stream handling login, heartbeat, and sequencing
- **Unified gateway** - Same protocol across all NYSE Group equities and options markets
- **Full lifecycle** - New, modify, cancel, mass cancel, reserve, hidden, and complex options orders
- **Correlated identifiers** - OrderIDs and DealIDs match Pillar market data feeds for reconciliation
- **Risk controls** - Built-in pre-trade price collars, size limits, and kill switches
- **Multi-asset support** - Supports equities, options, and complex multi-leg options orders

