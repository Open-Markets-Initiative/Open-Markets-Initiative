## C2Options Complex Depth Of Book: Cboe C2 Options Complex Strategy Full Depth Of Book

Full depth of book feed for complex multi-leg options strategies traded on Cboe C2 Options Exchange.

### Overview

Complex Depth Of Book is the full depth of book market data feed for the complex order book on Cboe C2 Options Exchange. It publishes order-by-order events for multi-leg options strategies, enabling subscribers to reconstruct the complete complex order book including spreads, straddles, and combinations.

Messages are delivered in the Cboe Pitch binary format over Ip multicast with A and B feed redundancy. Strategy definitions, trade reports, and auction events for the complex book are carried alongside the order events, and a Tcp gap request proxy service provides replay for missed multicast messages.

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of sequenced binary market data messages with per-packet sequence numbers and A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Full complex depth** - Order-by-order events for multi-leg strategies
- **Strategy definitions** - Complex instrument definitions published on the feed
- **Cboe Pitch** - Native Cboe binary message format
- **Multicast delivery** - Udp multicast with A and B feed redundancy
- **Complex auctions** - Auction messages for the complex order book
- **Gap request proxy** - Tcp recovery service for missed multicast messages

