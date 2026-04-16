## PhlxOptions Topo: Nasdaq Phlx Options Top Of Book Data

Top of book market data feed publishing best bid and offer quotations for options listed on the Nasdaq Phlx Options Exchange.

### Overview

Topo is the Nasdaq Phlx top of book market data feed, publishing best bid and offer quotations and trade reports for every option listed on the Nasdaq Phlx Options Exchange. It is a lightweight alternative to the full Market Depth feed.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Top of book** - Best bid and offer for Phlx options
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Phlx Options** - Coverage of Nasdaq Phlx listed options

