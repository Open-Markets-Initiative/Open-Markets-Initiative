## PsxEquities Nls Plus: Nasdaq Psx Equities Nasdaq Last Sale Plus

Consolidated last sale feed publishing trade print messages across Nasdaq listed and regional venues for Psx Equities.

### Overview

Nls Plus is the Nasdaq consolidated last sale feed, publishing trade print messages for instruments traded on Nasdaq and regional exchanges. It uses the Nasdaq Itch binary protocol over MoldUdp64 multicast.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Consolidated trades** - Cross market last sale messages for Psx Equities
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation
- **Psx Equities** - Coverage of Nasdaq Psx Equities listed instruments

