## Binary Umdf: B3 Sbe Market Data

Sbe-encoded binary market data protocol for disseminating real-time pricing and order book data on the B3 Brazilian exchange.

### Overview

Binary Umdf (Unified Market Data Feed) is B3's binary market data protocol delivering real-time order book, trade, and reference data for equities, derivatives, fixed income, and other instruments traded on the Brazilian exchange. The protocol uses Simple Binary Encoding (Sbe) for efficient binary message encoding with fixed-position, fixed-length fields.

The feed provides incremental order book updates, trade reports, instrument reference data, and trading status notifications. Binary Umdf supports both aggregate book views and detailed market data across multiple asset classes, with multicast dissemination for scalable distribution to subscribers.

### Transport

Udp multicast. Real-time incremental updates are disseminated on multicast groups with sequence numbers for gap detection. Snapshot and recovery feeds are available for initial book construction and gap recovery.

### Key Characteristics

- **Sbe encoded** - Fixed-position, fixed-length fields for zero-copy parsing
- **Multi-asset** - Covers equities, derivatives, fixed income, and other instruments
- **Incremental updates** - Real-time order book add, modify, and delete messages
- **Snapshot recovery** - Periodic full book snapshots for gap recovery and initial state
- **Trade reporting** - Last sale data with trade condition indicators
- **Sequence numbered** - Packets carry sequence numbers for gap detection
- **Schema versioned** - Xml Sbe templates define message layouts per version
