## NsmEquities Noi: Nasdaq Nsm Equities Net Order Imbalance Indicator

Net Order Imbalance Indicator feed publishing cross imbalance information for auction events for Nsm Equities.

### Overview

Net Order Imbalance is the auction imbalance feed, publishing buy and sell order imbalance information during opening, closing, and intra-day cross events. It uses the Nasdaq Itch binary protocol over MoldUdp64 multicast.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Auction imbalance** - Buy and sell imbalance quantities for crosses for Nsm Equities
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Nsm Equities** - Coverage of Nasdaq Nsm Equities listed instruments

