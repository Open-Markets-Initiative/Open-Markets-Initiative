## IseOptions Depth Of Market: Nasdaq Ise Options Depth Of Book Data

Full depth of book market data feed publishing order events for Ise Options.

### Overview

Depth Of Market is the full depth of book feed, publishing order add, modify, execute, and delete events for every instrument listed on the market. It uses the Nasdaq Itch binary protocol over MoldUdp64 multicast.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Full depth of book** - Order-by-order events for Ise Options
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Ise Options** - Coverage of Nasdaq Ise Options listed instruments

