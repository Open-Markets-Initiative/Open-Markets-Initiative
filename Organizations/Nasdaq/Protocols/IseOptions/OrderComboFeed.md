## IseOptions Order Combo Feed: Ise Order Combo Market Data Feed

Order-by-order combo strategy market data feed publishing multi-leg strategy order events for Ise listed options.

### Overview

Order-by-order combo strategy market data feed publishing multi-leg strategy order events for Ise listed options

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Order-by-order combo** - Individual combo strategy order events
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Strategy definitions** - Combo instrument reference data
- **Gap recovery** - SoupBinTcp based recovery service

