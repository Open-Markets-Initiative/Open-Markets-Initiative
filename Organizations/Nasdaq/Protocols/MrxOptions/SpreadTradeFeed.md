## MrxOptions Spread Trade Feed: Nasdaq MRX Complex Strategy Trade Report Feed

Real-time trade report feed for complex and spread strategies on MRX Options, publishing Complex Strategy Trade Report messages alongside the common system and administrative messages.

### Overview

Spread Trade Feed is the trade component of the Nasdaq MRX Spread Feed, publishing real-time Complex Strategy Trade Report messages for executed complex orders. It uses the Nasdaq Itch binary protocol over MoldUdp64 multicast.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers.

### Key Characteristics

- **Spread trade reporting** - Real-time complex strategy trade prints for MRX Options
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **MRX Options** - Coverage of Nasdaq MRX listed instruments

