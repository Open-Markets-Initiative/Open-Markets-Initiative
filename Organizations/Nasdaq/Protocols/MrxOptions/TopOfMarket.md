## MrxOptions Top Of Market: Nasdaq Mrx Options Best Bid And Offer Data

Top of book market data feed publishing best bid and offer quotations and trade reports for Mrx Options.

### Overview

Top Of Market is the top of book market data feed, publishing best bid and offer quotations and last sale trade reports. The feed uses the Nasdaq Itch binary protocol over MoldUdp64 multicast.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Top of book** - Best bid and offer for Mrx Options
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Mrx Options** - Coverage of Nasdaq Mrx Options listed instruments

