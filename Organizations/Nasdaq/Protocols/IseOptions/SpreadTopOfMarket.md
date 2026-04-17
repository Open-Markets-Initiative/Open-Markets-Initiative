## IseOptions Spread Top Of Market: Nasdaq Ise Options Complex Order Best Bid And Offer

Top of book market data feed for complex and spread orders publishing best bid and offer quotations for Ise Options.

### Overview

Spread Top Of Market is the top of book feed for complex and spread orders, publishing best bid and offer quotations. It uses the Nasdaq Itch binary protocol over MoldUdp64 multicast.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Spread top of book** - Best bid and offer for complex orders for Ise Options
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Ise Options** - Coverage of Nasdaq Ise Options listed instruments

