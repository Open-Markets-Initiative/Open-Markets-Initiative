## NomOptions Bono: Nasdaq Options Top Of Book Data, which the venue calls Bono

Top of book market data feed publishing best bid and offer quotations with aggregated size, last sale data and administrative messages for options traded on the Nasdaq Options Market.

### Overview

Bono, Best Of Nasdaq Options, is the top of book market data feed for the Nasdaq Options Market (Nom). The options system calculates and disseminates its best bid and offer with aggregated size from displayable order and quote interest, sending a quote two sided where both sides change and one sided where only one does, and reports last sale data with broken trades where a trade is broken on the day it is reported. Administrative messages carry timestamps, the options directory, security open and trading action. Its own specification states that it matches the Nasdaq Texas Options Top Of Market and Nasdaq Phlx Topo specifications, so this is Nom's equivalent of the Top Of Market feed the sibling venues declare under that name.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Top of book** - Best bid and offer with aggregated size for Nasdaq Options
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Last sale data** - Trade reports and same day broken trades

