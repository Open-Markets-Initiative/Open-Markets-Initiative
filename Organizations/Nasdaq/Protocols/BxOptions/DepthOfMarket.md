## BxOptions Depth Of Market: Nasdaq Bx Options Depth Of Book Data

Full depth of book market data feed publishing order events for options traded on the Nasdaq Bx Options Market.

### Overview

Depth Of Market is the Nasdaq Bx Options full depth of book feed, publishing order add, modify, execute, and delete events for every option listed on the Nasdaq Bx Options Market. It uses the Nasdaq Itch binary protocol over MoldUdp64 multicast.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Full depth of book** - Order-by-order events for Bx Options
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Bx Options** - Coverage of Nasdaq Bx listed options

