## IseOptions Spread Depth Of Market: Nasdaq Phlx Options Complex Order Depth Of Book

Depth of book market data feed for complex and spread orders for Phlx Options.

### Overview

Spread Depth is the full depth of book feed for complex and spread orders, publishing order events and resting book state. It uses the Nasdaq Itch binary protocol over MoldUdp64 multicast.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Spread depth** - Complex order book events for Phlx Options
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Phlx Options** - Coverage of Nasdaq Phlx Options listed instruments

