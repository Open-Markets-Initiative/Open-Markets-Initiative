## iMpact: Ice iMpact Multicast Feed

Proprietary binary market data protocol developed by Intercontinental Exchange for real-time dissemination of futures and options market data across all Ice exchanges via Udp multicast.

### Overview

The Ice iMpact Multicast Feed is Ice's primary market data distribution protocol, delivering real-time depth of book, trade, settlement, and reference data for futures and options traded across Ice exchanges worldwide. The protocol provides full order book depth with price level aggregation, trade messages, market snapshots, and administrative messages covering all Ice-listed products including energy, agriculture, financials, and equity index derivatives.

iMpact uses a binary message format with a common message header identifying the message type and body length. Messages are organized by market type, with each multicast group carrying data for a related set of products. The protocol supports both regular trading session data and strip and strategy trading including complex instrument definitions. Ice provides a Wireshark dissector and getting started documentation alongside the message specification.

The feed delivers data across multiple message categories including market snapshots for initial book construction, add/modify/delete price level messages for incremental book updates, trade messages, settlement prices, open interest, market state notifications, and pre-open price indicators. Strategy and strip-related messages support implied pricing and complex instrument definitions.

### Transport

Udp multicast. Each market type is assigned to dedicated multicast groups. Messages are sequenced within each multicast group for gap detection. A separate snapshot feed provides periodic full book state for recovery and late-joining clients. The protocol uses big-endian byte ordering for all binary fields.

### Key Characteristics

- **Binary encoding** - Fixed-length binary messages with big-endian byte ordering
- **Udp multicast delivery** - Real-time distribution via multicast groups organized by market type
- **Price level aggregation** - Order book depth at aggregated price levels with add/modify/delete updates
- **Sequenced messages** - Sequence numbers for gap detection within each multicast group
- **Snapshot recovery** - Separate snapshot feed for full book state recovery
- **Multi-asset class** - Energy, agriculture, financials, equity index, and environmental derivatives
- **Strategy support** - Complex instrument definitions and implied pricing for strips and strategies
- **Market state notifications** - Trading status, pre-open indicators, and session lifecycle events
