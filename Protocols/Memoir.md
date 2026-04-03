## Memoir: Members Exchange Information Record

Market data and order entry protocol suite developed by MEMX (Members Exchange), a member-owned US equities and options exchange, using FIX semantics with Simple Binary Encoding (SBE) for high-performance message delivery.

### Overview

Memoir is the market data protocol family for the Members Exchange (MEMX), providing real-time dissemination of order book, top-of-book, and trade information for equities and options. The protocol suite consists of three feeds: Memoir Depth for full depth-of-book, Memoir Top for best bid and offer, and Memoir Last Sale for real-time trade reports. MEMX also provides MEMO (Members Exchange Message for Orders), the companion order entry protocol available in SBE binary and FIX tag-value ASCII variants.

All MEMX protocols use FIX Protocol Standard semantics and leverage Simple Binary Encoding (SBE). MEMX provides XML schema definitions that can be compiled by any SBE codec to generate message encoders and decoders in languages such as Java, C++, and C#. MEMX was founded in 2019 by nine major financial organizations, launched equities trading in September 2020, and launched options trading in September 2023. The MEMX platform also powers the Long-Term Stock Exchange (LTSE).

### Transport

Memoir market data feeds are delivered via UDP multicast using redundant A/B multicast channels for reliability. Each feed is published on a pair of multicast addresses allowing subscribers to consume from either or both channels for gap detection and failover. The session layer uses MEMX-UDPA for multicast delivery. For order entry, MEMO uses MEMX-TCPA, a TCP-based session transport protocol providing reliable ordered delivery with built-in sequencing and session management.

### Key Characteristics

- **SBE encoding** - All Memoir and MEMO messages use Simple Binary Encoding for minimal serialization overhead
- **FIX semantics** - Message definitions follow FIX Protocol Standard field naming and semantics
- **Redundant A/B multicast** - Dual multicast feeds for market data reliability and gap detection
- **Three market data feeds** - Depth, Top, and Last Sale feeds serving different subscriber requirements
- **Dual order entry variants** - MEMO SBE for low-latency binary access and MEMO FIX for standard ASCII connectivity
- **Schema-driven code generation** - XML schema definitions enable automatic codec generation across multiple languages
- **Equities and options** - Protocols support both MEMX equities and MEMX Options markets
