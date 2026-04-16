## C1Options Complex Auction: Cboe Options Complex Order Auction Event Data

Auction event feed publishing complex order auction information for multi-leg options strategies on Cboe Options Exchange (C1).

### Overview

Complex Auction is the auction event feed for the complex order book on Cboe Options Exchange (C1), publishing opening, closing, and intraday auction messages for multi-leg options strategies. It carries indicative prices, imbalance quantities, and auction status for every complex strategy auction.

Messages are delivered in the Cboe Pitch binary format over Ip multicast with A and B feed redundancy. A companion Tcp gap request proxy service provides replay of missed multicast messages for subscribers that need gap recovery.

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of sequenced binary market data messages with per-packet sequence numbers and A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Complex auctions** - Auction events for multi-leg options strategies
- **Indicative prices** - Complex auction collar and imbalance information
- **Cboe Pitch** - Native Cboe binary message format
- **Multicast delivery** - Udp multicast with A and B feed redundancy
- **Gap request proxy** - Tcp recovery service for missed multicast messages

