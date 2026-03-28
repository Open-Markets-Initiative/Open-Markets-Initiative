## EOBI: Enhanced Order Book Interface

Low-latency binary market data protocol developed by Deutsche Borse for the T7 trading platform, providing full order-by-order visibility into the order book without any depth restriction.

### Overview

The Enhanced Order Book Interface (EOBI) is the premium market data feed of the T7 trading system operated by Deutsche Borse Group. It delivers un-netted, tick-by-tick order and trade information, giving subscribers complete transparency into every visible order and quote side in the book. Each individual order add, modify, delete, and execution event is published in real time, enabling participants to reconstruct the full order book at any point.

EOBI is designed for latency-sensitive market participants such as proprietary trading firms and market makers who require the fastest possible access to order book changes. Unlike aggregated market data feeds, EOBI transmits individual order-level events providing the highest granularity of market data available on T7 venues. The protocol uses FIX 5.0 SP2 application-level semantics but employs a proprietary flat binary encoding rather than FAST encoding, minimizing both message size and decode latency.

Messages are organized into incremental and snapshot channels, where incremental messages carry real-time order book updates and snapshot channels provide periodic full order book state for recovery and initial synchronization. EOBI is deployed across all T7-powered venues including Eurex, Xetra, EEX, and partner exchanges in Vienna, Budapest, Prague, Ljubljana, Zagreb, Sofia, and Malta.

### Transport

EOBI distributes data via UDP multicast. Each product is assigned to a specific multicast group, with separate multicast addresses for the incremental feed and the snapshot feed. Participants subscribe to the incremental channel for real-time updates and use the snapshot channel to build or recover the initial order book state. Each datagram contains a packet header followed by one or more messages identified by TemplateID and carrying a message sequence number for gap detection.

### Key Characteristics

- **Full depth of book** - Every visible order and quote side is published with no depth restriction
- **Order-by-order granularity** - Individual order add, modify, delete, and execution events rather than aggregated price levels
- **Flat binary encoding** - Proprietary binary format following FIX 5.0 SP2 semantics for minimal latency
- **UDP multicast delivery** - Real-time distribution via multicast with separate incremental and snapshot channels
- **Un-netted updates** - Each event is published individually with no netting or batching of order book changes
- **Sequenced messages** - Message sequence numbers on every message for gap detection and recovery
- **Priority timestamp** - Each order carries a priority timestamp enabling precise queue position determination
- **Ultra-low latency** - Designed as the lowest-latency market data interface on T7
