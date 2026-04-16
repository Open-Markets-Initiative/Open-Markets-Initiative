## NsmEquities Aggregated: Nasdaq Aggregated Depth Of Book Data

Aggregated price-level depth of book feed publishing top price levels for securities traded on the Nasdaq Stock Market.

### Overview

Aggregated is a Nasdaq market data feed for the Nasdaq Stock Market, delivered using the Nasdaq Itch binary protocol over MoldUdp64 multicast with SoupBinTcp glimpse and retransmission services for recovery.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Retransmission** - SoupBinTcp recovery for missed multicast
- **Nasdaq Stock Market** - Coverage of Nasdaq listed securities

