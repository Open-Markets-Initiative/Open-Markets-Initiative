## IseOptions Depth Combo Feed: Ise Depth Combo Market Data Feed

Aggregated depth of book combo feed publishing multi-leg strategy order book events for options traded on the Nasdaq Ise Options Exchange.

### Overview

Aggregated depth of book combo feed publishing multi-leg strategy order book events for options published for options traded on the Nasdaq Ise Options Exchange

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Depth of book** - Aggregated price levels for combo strategies
- **Multi-leg support** - Combo order book events
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Reference data** - Strategy definitions
- **Gap recovery** - SoupBinTcp based recovery service

