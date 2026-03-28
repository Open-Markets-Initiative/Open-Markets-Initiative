## BinaryEntryPoint: B3 Binary Entry Point

Binary order entry protocol developed by B3 (Brasil Bolsa Balcao) for submitting and managing orders on the PUMA Trading System, using Simple Binary Encoding over a FIXP session layer.

### Overview

Binary EntryPoint is B3's current-generation order entry API for trading equities, derivatives, fixed income, and FX products on the PUMA Trading System. It replaced the older FIX 4.4 tag-value-based EntryPoint protocol with a modern binary encoding based on Simple Binary Encoding (SBE), providing significantly lower encoding and decoding latency. The protocol uses little-endian byte ordering for all numeric fields.

Binary EntryPoint is structured as two distinct layers: a session layer based on the FIX Performance Session Protocol (FIXP), and a business layer carrying order entry and execution messages in SBE format. The FIXP session layer handles connection management, sequencing, and keepalive negotiation. Session establishment follows a Negotiate and Establish handshake where the client initiates communication with the B3 gateway.

The protocol supports multiple order types including standard new orders, simplified new orders with predefined defaults, order modifications, cancellations, cross orders, and mass quoting for market makers. B3 provides detailed certification scripts that trading participants must complete before production access.

### Transport

Binary EntryPoint operates over TCP for reliable ordered message delivery between client systems and B3 PUMA Trading System gateways. The FIXP session layer provides negotiation, establishment with sequence number synchronization, bidirectional sequencing, keepalive heartbeats, retransmission of missed messages, and graceful session termination.

### Key Characteristics

- **SBE encoded** - Simple Binary Encoding for ultra-low latency encoding and decoding
- **FIXP session layer** - FIX Performance protocol for lightweight session management
- **Fixed message sizes** - Standard message layouts with fixed positions and fixed-length fields
- **Little-endian byte order** - Least significant byte first for all numeric fields
- **Simple and standard order types** - SimpleNewOrder for common cases and NewOrderSingle for full flexibility
- **Mass quoting** - Efficient bulk quoting for market makers
- **Schema versioned** - SBE XML templates define message layouts per specification version
- **Certification required** - Trading participants must complete B3 certification scripts before production access
