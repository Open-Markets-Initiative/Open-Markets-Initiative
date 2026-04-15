## IseOptions Order Feed: Ise Order Feed Market Data

Order-by-order market data feed publishing individual order events for options traded on the Nasdaq Ise Options Exchange.

### Overview

Order-by-order market data feed publishing individual order events for options published for options traded on the Nasdaq Ise Options Exchange

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Order-by-order** - Add, modify, execute, delete events
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Full order book** - Complete limit order book reconstruction
- **Gap recovery** - SoupBinTcp based recovery service

