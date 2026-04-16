## NomOptions Itto: Nasdaq Options Top Order Market Data

Top of book Itch-based market data feed publishing best bid and offer quotations and trade reports for options traded on the Nasdaq Options Market.

### Overview

Itto is the top of book market data feed for the Nasdaq Options Market (Nom), publishing best bid and offer updates plus trade reports for every listed option using the Nasdaq Itch binary protocol. The feed is delivered over MoldUdp64 multicast with a SoupBinTcp glimpse snapshot and retransmission service for recovery.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Top of book** - Best bid and offer for Nasdaq Options
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Options market data** - Coverage of all listed Nom options

