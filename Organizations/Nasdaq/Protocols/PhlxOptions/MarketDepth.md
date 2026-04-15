## PhlxOptions Market Depth: Nasdaq Phlx Options Depth Of Book Data

Full depth of book market data feed publishing order events for options listed on the Nasdaq Phlx Options Exchange.

### Overview

Market Depth is the Nasdaq Phlx full depth of book feed, publishing order add, modify, execute, and delete events for every option listed on the Nasdaq Phlx Options Exchange. The feed uses the Nasdaq Itch binary protocol over MoldUdp64 multicast.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Full depth of book** - Order-by-order events
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Phlx Options** - Coverage of Nasdaq Phlx listed options

