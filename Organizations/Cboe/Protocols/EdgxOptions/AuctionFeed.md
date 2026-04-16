## EdgxOptions Auction Feed: Cboe EDGX Options Auction Event Data

Dedicated auction event feed publishing opening, closing, and intraday auction information for options traded on Cboe EDGX Options Exchange.

### Overview

Auction Feed is a dedicated market data product that publishes auction information for Cboe EDGX Options Exchange, including opening auction, closing auction, volatility auction, and price improvement auction events. It carries the indicative prices, imbalance quantities, and auction status messages that market participants rely on to trade auctions intelligently.

Messages are delivered in the Cboe Pitch binary format over Ip multicast with A and B feed redundancy, and a companion Tcp gap request proxy service provides replay of missed multicast messages. The feed is unidirectional market data and cannot be used to submit orders.

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of sequenced binary market data messages with per-packet sequence numbers and A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Auction events** - Opening, closing, and intraday auction messages
- **Indicative prices** - Auction collar and imbalance information
- **Cboe Pitch** - Native Cboe binary message format
- **Multicast delivery** - Udp multicast with A and B feed redundancy
- **Gap request proxy** - Tcp recovery service for missed multicast messages

