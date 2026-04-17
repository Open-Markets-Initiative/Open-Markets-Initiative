## NsmEquities Qbbo: Nasdaq Nsm Equities Attributed Best Bid And Offer

Top of book market data feed publishing attributed best bid and offer quotations with participant identification for Nsm Equities.

### Overview

Qbbo is the attributed top of book feed, publishing best bid and offer quotations with participant attribution. It uses the Nasdaq Itch binary protocol over MoldUdp64 multicast.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Attributed quotes** - Best bid and offer with participant identification for Nsm Equities
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Nsm Equities** - Coverage of Nasdaq Nsm Equities listed instruments

