## GemxOptions Order Feed: Nasdaq Gemx Options Order Level Market Data

Order-level market data feed publishing order add, modify, cancel, and execute events for options traded on the Nasdaq Gemx Options Market.

### Overview

Order Feed is the Nasdaq Gemx Options order-level market data feed, publishing individual order add, modify, cancel, and execute events for every option listed on the Nasdaq Gemx Options Market. It uses the Nasdaq Itch binary protocol over MoldUdp64 multicast.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary order events with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Order level** - Individual order add, modify, cancel, and execute events
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Gemx Options** - Coverage of Nasdaq Gemx listed options

