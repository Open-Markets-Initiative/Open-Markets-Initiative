## Eobi: Enhanced Order Book Interface

Binary market data protocol providing order-by-order depth of book data from the Eurex T7 trading platform for derivatives and cash equity instruments.

### Overview

Eobi (Enhanced Order Book Interface) is Deutsche Boerse's high-performance market data feed for the T7 trading platform, delivering order-level book transparency for Eurex derivatives and Xetra/Boerse Frankfurt cash equities. The protocol disseminates every individual order add, modify, and delete event in the central order book, providing the most granular view of market microstructure available from T7.

Eobi offers full order-by-order depth showing individual order priority and queue position, which is critical for participants requiring precise book reconstruction. The feed also includes execution summaries, trade reports, instrument status changes, and product-level statistics. Eobi operates alongside the aggregate Emdi (Enhanced Market Data Interface) and provides a superset of information by exposing individual order identifiers and their lifecycle events.

### Transport

Udp multicast delivery on dedicated market data network infrastructure. Messages are organized by product partition and disseminated on separate multicast groups. Sequence numbers enable gap detection, and snapshot feeds provide periodic full book state for recovery.

### Key Characteristics

- **Order-by-order depth** - Individual order visibility with priority and queue position
- **T7 platform** - Market data from Eurex derivatives and cash equity matching engines
- **Full order lifecycle** - Add, modify, delete, and execution events for every order
- **Product partitioned** - Data organized by product partition on separate multicast groups
- **Execution summaries** - Aggregated match event information at trade completion
- **Snapshot recovery** - Periodic full book state dissemination for gap recovery
- **Instrument status** - Trading state changes and auction phase notifications
