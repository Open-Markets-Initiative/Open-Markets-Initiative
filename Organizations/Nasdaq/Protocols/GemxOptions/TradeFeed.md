## GemxOptions Trade Feed: Nasdaq Gemx Options Trade Report Data

Trade report feed publishing last sale and trade print messages for options traded on the Nasdaq Gemx Options Market.

### Overview

Trade Feed is the Nasdaq Gemx Options last sale market data feed, publishing trade print messages for every option listed on the Nasdaq Gemx Options Market. It uses the Nasdaq Itch binary protocol over MoldUdp64 multicast.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary trade messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Trade reports** - Last sale and trade print messages for Gemx Options
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Gemx Options** - Coverage of Nasdaq Gemx listed options

