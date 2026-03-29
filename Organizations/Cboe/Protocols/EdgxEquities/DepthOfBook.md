## Cboe Edgx Equities Depth Of Book

Pitch multicast feed providing full order-level depth of book for Cboe Edgx Equities Exchange.

### Overview

Equities Depth Of Book delivers real-time order-by-order market data for all instruments traded on Cboe Edgx Equities Exchange. The feed shows individual order add, modify, and cancel activity, enabling subscribers to reconstruct the full limit order book at every price level.

The feed is the primary source for participants requiring complete book visibility on the Edgx equity exchange. Messages include order priority information, execution reports, and trade break notifications.

### Transport

Udp multicast with sequenced delivery and spin server gap recovery.

### Key Characteristics

- **Order-level granularity** - Individual order activity visible for full book reconstruction
- **Real-time executions** - Trade messages with price, quantity, and condition codes
- **Sequenced multicast** - Sequence numbers on all messages for gap detection
