## UMDF: B3 Unified Market Data Feed

Binary market data protocol developed by B3 (Brasil Bolsa Balcao) for disseminating real-time and recovery market data across equities, derivatives, fixed income, and FX markets on the PUMA Trading System using Simple Binary Encoding over multicast UDP.

### Overview

Binary UMDF is B3's current-generation market data feed, delivering real-time pricing, order book depth, instrument definitions, and trading status for all asset classes traded on the PUMA Trading System. The protocol uses Simple Binary Encoding (SBE) based on FIX SBE version 1.0, providing fixed-position, fixed-length fields optimized for low-latency encoding and decoding. Binary UMDF replaced the older UMDF FIX/FAST-based feed.

Market data is organized into channels, each carrying data for a related group of instruments. Each channel is logically divided into three streams: an Incremental Stream for real-time updates, an Instrument Definition Stream for security reference data broadcast on a continuous loop, and a Snapshot Recovery Stream for periodic full state recovery. B3 employs a dual-feed architecture where Feed A provides all three streams and Feed B provides a redundant copy of the Incremental Stream.

Binary UMDF supports both Market by Order (MBO) full order-level depth and Market by Event (MBE) aggregate views. The protocol uses little-endian byte ordering, and packets are constrained to 1400 bytes or fewer for VPN compatibility. Each UDP datagram contains a Packet Header followed by one or more SBE-encoded messages.

### Transport

Binary UMDF operates over UDP multicast for real-time market data delivery. Each channel provides multiple feed types on dedicated multicast groups: an Incremental Stream on Feed A and Feed B, an Instrument Definition Stream on Feed A, and a Snapshot Recovery Stream on Feed A. B3 recommends that clients subscribe to both Feed A and Feed B simultaneously for increased reliability.

### Key Characteristics

- **SBE encoded** - Simple Binary Encoding with fixed-position, fixed-length fields for low-latency parsing
- **Dual-feed redundancy** - Feed A and Feed B disseminate identical incremental data for failover
- **Channel architecture** - Instruments organized into channels by market segment
- **Market by Order and Market by Event** - Supports full order-level depth and aggregate book views
- **Sequence numbered** - Every packet carries sequence numbers for gap detection and recovery
- **Little-endian byte order** - Least significant byte first for all numeric fields
- **1400-byte packet limit** - Maximum datagram size ensures VPN compatibility
- **Schema versioned** - SBE XML templates define message layouts for each specification version
