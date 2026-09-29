## NsmEquities Total View Plus: Nasdaq Multi Market Full Depth Of Book Market Data

Full depth of book Itch-based market data feed publishing order-by-order events for equities traded on the Nasdaq, Nasdaq Texas and Nasdaq PSX execution systems on one feed.

### Overview

TotalView Plus is the full depth of book market data feed covering the Nasdaq, Nasdaq Texas and Nasdaq PSX execution systems, publishing order-by-order events using the Nasdaq Itch binary protocol. The feed delivers order add, modify, execute, and delete messages enabling subscribers to reconstruct the limit order book of each market center for every listed equity instrument.

Every message opens with a one byte Market/Session Indicator naming the Nasdaq Extended Session, the Nasdaq Core Session, Nasdaq Texas or PSX, ahead of the message type. Timestamps are nanoseconds since the Unix epoch, and stock locates, order reference numbers and match numbers are unique only within a market center or session.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp, plain or compressed, for sequenced delivery of the same messages.

### Key Characteristics

- **Full depth of book** - Order-by-order add, modify, execute, and delete events
- **Multiple market centers** - Nasdaq, Nasdaq Texas and PSX on one feed, told apart by the Market/Session Indicator
- **24 hour sessions** - Nasdaq Extended Session (9:00 PM - 4:00 AM ET) beside the Nasdaq Core Session
- **Nasdaq Itch** - Industry-standard Itch binary message format
- **MoldUdp64** - Packaged over the Nasdaq MoldUdp64 multicast framing
- **Epoch timestamps** - Eight byte nanoseconds since the Unix epoch, UTC

