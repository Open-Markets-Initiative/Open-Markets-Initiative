## C1Options Complex Top: Cboe Options Complex Strategy Top Of Book

Top of book feed for complex multi-leg options strategies traded on Cboe Options Exchange (C1).

### Overview

Complex Top is the top of book market data feed for the complex order book on Cboe Options Exchange (C1), publishing best bid and offer quotations for multi-leg options strategies including spreads, straddles, and combinations. The feed also carries trade reports for executed complex orders and strategy definition messages.

Messages are delivered in the Cboe Pitch binary format over Ip multicast with A and B feed redundancy. A companion Tcp gap request proxy service provides replay of missed multicast messages for subscribers that need gap recovery.

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of sequenced binary market data messages with per-packet sequence numbers and A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Complex book** - Top of book for multi-leg options strategies
- **Strategy definitions** - Complex instrument definitions published on the feed
- **Cboe Pitch** - Native Cboe binary message format
- **Multicast delivery** - Udp multicast with A and B feed redundancy
- **Trade reports** - Last sale messages for executed complex trades
- **Gap request proxy** - Tcp recovery service for missed multicast messages

