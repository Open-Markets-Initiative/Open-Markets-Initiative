## LastSale Itch: BruceAts Equities Market Data

Equities last sale Itch feed providing trade execution data on BruceAts.

### Overview

LastSale Itch is the trade reporting market data feed for equities traded on the Bruce alternative trading system. The feed disseminates real-time trade execution messages with price, size, and trade condition indicators for all executed trades on the venue.

The protocol delivers trade-only data using compact binary-encoded messages over multicast. Subscribers requiring trade execution information without order book data use this feed as a focused alternative to the full depth of book feed.

### Transport

Udp multicast with sequence numbers for gap detection and message ordering.

### Key Characteristics

- **Trade reporting** - Real-time last sale data for all executed trades
- **Lightweight** - Trade-only feed without order book overhead
- **Binary encoded** - Compact fixed-length messages for efficient processing
- **Equities** - Covers all equity instruments on BruceAts
