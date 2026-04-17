## MrxOptions Trade Feed: Nasdaq Mrx Options Trade Report Data

Trade report feed publishing last sale and trade print messages for Mrx Options.

### Overview

Trade Feed is the last sale market data feed, publishing trade print messages. It uses the Nasdaq Itch binary protocol over MoldUdp64 multicast.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Trade reports** - Last sale and trade print messages for Mrx Options
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Mrx Options** - Coverage of Nasdaq Mrx Options listed instruments

