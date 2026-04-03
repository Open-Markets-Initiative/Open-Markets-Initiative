## BestBidAndOffer Itch: BruceAts Equities Market Data

Equities Bbo Itch feed providing top of book pricing on BruceAts.

### Overview

BestBidAndOffer Itch is the top of book market data feed for equities traded on the Bruce alternative trading system. The feed disseminates real-time best bid and offer updates with associated sizes, providing a lightweight view of current pricing without full order book depth.

The protocol delivers Bbo quote updates and trade summary data using compact binary-encoded messages over multicast. Subscribers requiring only top of book pricing use this feed as an efficient alternative to the full depth of book feed.

### Transport

Udp multicast with sequence numbers for gap detection and message ordering.

### Key Characteristics

- **Top of book** - Best bid and offer quotes with associated sizes
- **Lightweight** - Focused Bbo updates without full depth overhead
- **Binary encoded** - Compact fixed-length messages for efficient processing
- **Equities** - Covers all equity instruments on BruceAts
