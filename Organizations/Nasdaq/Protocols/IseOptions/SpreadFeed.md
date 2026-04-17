## IseOptions Spread Feed: Nasdaq Ise Options Complex Order Feed

Market data feed for complex and spread order events for Ise Options.

### Overview

Spread Feed is the complex order market data feed, publishing spread order add, modify, cancel, and execute events. It uses the Nasdaq Itch binary protocol over MoldUdp64 multicast.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Spread feed** - Complex order events for Ise Options
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Ise Options** - Coverage of Nasdaq Ise Options listed instruments

