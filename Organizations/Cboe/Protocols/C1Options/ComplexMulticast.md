## C1Options Complex Multicast: Cboe Options Complex Strategy Multicast Market Data

Udp multicast feed publishing complex strategy market data for Cboe Options Exchange (C1).

### Overview

Complex Multicast is the primary multicast market data feed for the complex order book on Cboe Options Exchange (C1). It bundles the top of book and depth of book events for complex strategies into a single multicast stream, simplifying subscriber integration while still providing full visibility into the complex book.

Messages are delivered in the Cboe Pitch binary format over Ip multicast with A and B feed redundancy. A companion Tcp gap request proxy service provides replay for subscribers that miss packets on the multicast feed.

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of sequenced binary market data messages with per-packet sequence numbers and A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Bundled complex feed** - Top and depth of book for complex strategies
- **Cboe Pitch** - Native Cboe binary message format
- **Multicast delivery** - Udp multicast with A and B feed redundancy
- **Gap request proxy** - Tcp recovery service for missed multicast messages

