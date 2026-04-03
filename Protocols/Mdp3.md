## MDP3: CME Market Data Platform 3.0

Binary market data protocol developed by CME Group for disseminating real-time and recovery market data across CME, CBOT, NYMEX, and COMEX exchanges using Simple Binary Encoding over multicast UDP.

### Overview

MDP 3.0 is CME Group's event-based market data platform that delivers real-time pricing, order book, and reference data for futures, options, spreads, and FX instruments traded on CME Globex. The protocol uses Simple Binary Encoding (SBE) based on the FIX 5.0 SP2 message specification, providing fixed-position, fixed-length fields for efficient direct access to data without sequential parsing.

The platform employs a dual-feed, multicast UDP architecture where Feed A and Feed B simultaneously disseminate identical data on separate multicast addresses for redundancy. Market data is organized into channels, each carrying data for a related group of instruments. MDP 3.0 supports both Market by Price (MBP) aggregate book views and Market by Order (MBO) full order-level depth.

MDP 3.0 also offers conflated feeds for lower-bandwidth consumption, including a 50-millisecond conflated UDP feed and a conflated TCP market data group for clients that do not require tick-by-tick granularity. CME Group publishes SBE schema template files for all operating environments on public FTP servers.

### Transport

MDP 3.0 operates over UDP multicast for real-time market data delivery. Each channel provides multiple feed types on dedicated multicast groups: an Incremental Feed for real-time updates on Feed A and Feed B, an Instrument Definition Feed broadcasting security definitions on a continuous loop, and a Snapshot/Recovery Feed providing periodic full book snapshots for recovery and late-joining clients.

### Key Characteristics

- **SBE encoded** - Simple Binary Encoding with fixed-position, fixed-length fields for zero-copy parsing
- **Dual-feed redundancy** - Feed A and Feed B disseminate identical data for failover
- **Event-based messaging** - Messages grouped by match events with end-of-event indicators
- **Channel architecture** - Instruments organized into channels by product group
- **Market by Price and Market by Order** - Supports both aggregate and full order-level book depth
- **Sequence numbered** - Every packet carries sequence numbers for gap detection
- **Schema versioned** - XML-based SBE templates define message layouts per schema version
