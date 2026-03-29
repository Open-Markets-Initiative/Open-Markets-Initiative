## Cboe Options Market Level 2

Csm feed providing aggregate price level depth for options series on Cboe Options Exchange.

### Overview

Options Market Level 2 delivers aggregated order book data at each price level for options series traded on Cboe Options Exchange. The feed provides total quantity available at each price point using the Csm protocol, giving subscribers a compact depth view without individual order detail.

The feed serves participants who need depth visibility beyond top of book for options series but do not require order-level granularity. It provides a bandwidth-efficient alternative to full depth feeds while conveying meaningful book structure at multiple price levels.

### Transport

Udp multicast delivery organized by product group with recovery mechanisms for gap handling.

### Key Characteristics

- **Price level depth** - Aggregate quantity at each price point for options series
- **Csm protocol** - Delivered using the Csm streaming market data framework
- **Reduced bandwidth** - Compact depth without individual order-level detail
- **Multi-level visibility** - Book depth beyond top of book across price levels
