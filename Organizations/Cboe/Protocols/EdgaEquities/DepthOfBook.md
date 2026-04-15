## EdgaEquities Depth Of Book: Cboe EDGA Full Depth Of Book Data

Full depth of book Pitch feed publishing order add, modify, cancel, and execute events for equities traded on Cboe US Equities EDGA Exchange.

### Overview

Depth Of Book is the full depth of book market data feed for Cboe US Equities EDGA Exchange, delivered in the Cboe Pitch binary message format. The feed publishes order-by-order events including add, modify, delete, and execute messages so that subscribers can reconstruct the complete order book for every listed equity instrument.

Messages are distributed over Ip multicast with A and B feed redundancy and complemented by a Tcp gap request proxy service for recovery of missed multicast messages. Trade reports, auction events, and trading status updates are carried inline with the order events for a complete view of the market.

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of sequenced binary market data messages with per-packet sequence numbers and A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Full depth of book** - Order-by-order add, modify, cancel, and execute events
- **Cboe Pitch** - Native Cboe binary message format
- **Multicast delivery** - Udp multicast with A and B feed redundancy
- **Trade reports** - Last sale messages published alongside order events
- **Auction events** - Opening, closing, and intraday auction messages
- **Gap request proxy** - Tcp recovery service for missed multicast messages
- **Trading status** - System event and instrument-level status notifications

