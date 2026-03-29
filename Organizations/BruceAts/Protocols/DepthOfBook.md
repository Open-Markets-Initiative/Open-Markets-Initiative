## DepthOfBook Itch: BruceAts Equities Market Data

Equities depth of book Itch feed providing full order book data on BruceAts.

### Overview

DepthOfBook Itch is the full depth market data feed for equities traded on the Bruce alternative trading system. The feed delivers order-by-order messages including individual add, modify, and delete events, enabling subscribers to reconstruct the complete order book at every price level.

The protocol provides granular order-level detail for building and maintaining accurate book state throughout the trading session. Subscribers requiring full depth of book visibility use this feed for pricing, execution, and surveillance applications.

### Transport

Udp multicast with sequence numbers for gap detection and message ordering.

### Key Characteristics

- **Full depth of book** - Every order visible at every price level
- **Order-by-order** - Individual order events for complete book reconstruction
- **Binary encoded** - Compact fixed-length messages for efficient processing
- **Equities** - Covers all equity instruments on BruceAts
