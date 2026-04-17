## MrxOptions Order Feed: Nasdaq Mrx Options Order Level Market Data

Order-level market data feed publishing order add, modify, cancel, and execute events for Mrx Options.

### Overview

Order Feed is the order-level market data feed, publishing individual order add, modify, cancel, and execute events. It uses the Nasdaq Itch binary protocol over MoldUdp64 multicast.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Order level** - Individual order events for Mrx Options
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Mrx Options** - Coverage of Nasdaq Mrx Options listed instruments

