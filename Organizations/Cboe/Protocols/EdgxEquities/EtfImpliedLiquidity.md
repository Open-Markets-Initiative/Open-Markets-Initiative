## EdgxEquities Etf Implied Liquidity: Cboe EDGX Etf Implied Liquidity Data

Specialised feed publishing implied liquidity values for exchange traded funds on Cboe US Equities EDGX Exchange.

### Overview

Etf Implied Liquidity is a specialised market data product for Cboe US Equities EDGX Exchange that publishes implied liquidity metrics for exchange traded funds. Implied liquidity measures the quantity of an Etf that can be traded based on the underlying basket liquidity rather than the Etf quote directly, giving market participants a more realistic view of tradable size.

The feed is delivered in the Cboe Pitch binary format over Ip multicast with A and B feed redundancy. A Tcp gap request proxy service is available for recovery of messages missed on the multicast feed.

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of sequenced binary market data messages with per-packet sequence numbers and A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Etf implied liquidity** - Basket-derived liquidity metrics for Etfs
- **Specialised feed** - Dedicated product for Etf tradable size
- **Cboe Pitch** - Native Cboe binary message format
- **Multicast delivery** - Udp multicast with A and B feed redundancy
- **Gap request proxy** - Tcp recovery service for missed multicast messages

