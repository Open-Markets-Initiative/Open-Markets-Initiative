## NtxOptions Top Of Market: Nasdaq Ntx Options Best Bid And Offer Data

Top of book market data feed publishing best bid and offer quotations and trade reports for Ntx Options.

### Overview

Top Of Market is the top of book market data feed, publishing best bid and offer quotations and last sale trade reports. The feed uses the Nasdaq Itch binary protocol over MoldUdp64 multicast.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Top of book** - Best bid and offer for Ntx Options
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Ntx Options** - Coverage of Nasdaq Ntx Options listed instruments

