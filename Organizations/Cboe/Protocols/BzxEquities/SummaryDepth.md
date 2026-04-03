## Cboe Bzx Equities Summary Depth

Pitch feed providing aggregate price level depth for Cboe Bzx Equities Exchange.

### Overview

Equities Summary Depth delivers aggregated order book data at each price level rather than individual order detail. The feed provides total quantity available at each price point, giving subscribers a compact view of market depth without the message volume of full order-level feeds.

The feed serves participants who need depth visibility beyond top of book but do not require individual order tracking. It reduces bandwidth and processing requirements compared to the full depth of book feed while still conveying meaningful book structure.

### Transport

Udp multicast with sequenced delivery and spin server gap recovery.

### Key Characteristics

- **Price level aggregation** - Total quantity at each price point rather than individual orders
- **Reduced bandwidth** - Compact depth representation with lower message rates
- **Multi-level depth** - Visibility beyond top of book across multiple price levels
- **Real-time updates** - Aggregate quantities refreshed as book changes occur
