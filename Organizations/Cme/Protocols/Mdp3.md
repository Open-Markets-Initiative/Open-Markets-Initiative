## Mdp 3.0: Cme Market Data Platform

Binary market data protocol for disseminating real-time and recovery market data across Cme, Cbot, Nymex, and Comex using Sbe encoding over multicast Udp.

### Overview

Mdp 3.0 is Cme Group's event-based market data platform delivering real-time pricing, order book, and reference data for futures, options, spreads, and Fx instruments traded on Cme Globex. The protocol uses Sbe encoding based on Fix 5.0 Sp2, providing fixed-position, fixed-length fields for efficient direct access without sequential parsing.

The platform employs a dual-feed multicast Udp architecture where Feed A and Feed B simultaneously disseminate identical data on separate multicast addresses. Market data is organized into channels by product group. Mdp 3.0 supports both Market by Price (Mbp) aggregate book views and Market by Order (Mbo) full order-level depth. Conflated feeds are available for lower-bandwidth consumption.

### Transport

Udp multicast. Each channel provides an Incremental Feed (Feed A and Feed B), an Instrument Definition Feed on continuous loop, and a Snapshot/Recovery Feed for periodic full book state. Packets carry sequence numbers for gap detection.

### Key Characteristics

- **Sbe encoded** - Fixed-position, fixed-length fields for zero-copy parsing
- **Dual-feed redundancy** - Feed A and Feed B disseminate identical data for failover
- **Event-based messaging** - Messages grouped by match events with end-of-event indicators
- **Channel architecture** - Instruments organized into channels by product group
- **Market by Price and Market by Order** - Both aggregate and full order-level book depth
- **Sequence numbered** - Every packet carries sequence numbers for gap detection
- **Schema versioned** - Xml Sbe templates define message layouts per version
