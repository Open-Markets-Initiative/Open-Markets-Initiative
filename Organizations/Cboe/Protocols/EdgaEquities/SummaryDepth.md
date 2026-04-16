## EdgaEquities Summary Depth: Cboe EDGA Aggregated Price Level Depth Of Book

Aggregated price level depth of book feed for equities traded on Cboe US Equities EDGA Exchange, delivering top price levels instead of full order-by-order events.

### Overview

Summary Depth is the aggregated price level market data feed for Cboe US Equities EDGA Exchange, publishing order book state at the price-level aggregated tier rather than per-order. It delivers compact updates when aggregate size at a price level changes, making it suitable for subscribers that need depth information without the full volume of the order-by-order Pitch feed.

Messages are distributed over Ip multicast with A and B feed redundancy. Trade reports, auction events, and trading status updates are carried alongside the depth updates, and a Tcp gap request proxy service provides replay of messages missed on the multicast feed.

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of sequenced binary market data messages with per-packet sequence numbers and A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Aggregated depth** - Price level book state rather than per-order events
- **Cboe Pitch** - Native Cboe binary message format
- **Multicast delivery** - Udp multicast with A and B feed redundancy
- **Top levels** - Focused on the most traded price levels for bandwidth efficiency
- **Gap request proxy** - Tcp recovery service for missed multicast messages
- **Trade reports** - Last sale messages published alongside depth updates

