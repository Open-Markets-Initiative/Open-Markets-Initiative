## NsmEquities Nls Plus: Nasdaq Consolidated Last Sale Data

Consolidated last sale feed publishing trade reports for Nasdaq-listed securities with additional trade attributes and conditions.

### Overview

NlsPlus is a Nasdaq market data feed for the Nasdaq Stock Market, delivered using the Nasdaq Itch binary protocol over MoldUdp64 multicast with SoupBinTcp glimpse and retransmission services for recovery.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Retransmission** - SoupBinTcp recovery for missed multicast
- **Nasdaq Stock Market** - Coverage of Nasdaq listed securities

