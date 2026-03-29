## Binary Entry Point: B3 Sbe/Fixp Order Entry

Sbe-encoded binary order entry protocol with Fixp session layer for submitting and managing orders on the B3 Brazilian exchange.

### Overview

Binary Entry Point is B3's binary order entry protocol for electronic trading of equities, derivatives, fixed income, and other instruments on the Brazilian exchange. The protocol uses Simple Binary Encoding (Sbe) for application-layer messages over a Fix Performance Session Protocol (Fixp) session layer, providing both low-latency binary encoding and robust session management.

The Fixp session layer handles connection negotiation, establishment, sequencing, and keepalive without embedding administrative overhead in business messages. The Sbe application layer carries order entry, modification, cancellation, and execution report messages with fixed-position, fixed-length fields for efficient direct-access parsing.

### Transport

Tcp to B3 matching engine gateways. Fixp session layer provides negotiation, establishment with sequence number synchronization, bidirectional sequencing, keepalive heartbeats, and graceful termination.

### Key Characteristics

- **Sbe encoded** - Fixed-position, fixed-length fields for zero-copy parsing
- **Fixp session layer** - Lightweight session protocol for sequencing and keepalive
- **Multi-asset** - Supports equities, derivatives, fixed income, and other instruments
- **Full order lifecycle** - New order, modify, cancel, and execution report messages
- **Sequenced messaging** - Bidirectional sequence numbers for reliable delivery
- **Schema versioned** - Xml Sbe templates define message layouts per version
