## IseOptions Spread Trade Feed: Nasdaq ISE Complex Strategy Trade Report Feed

Real-time trade report feed for complex and spread strategies on ISE Options, publishing Complex Strategy Trade Report messages alongside the common system and administrative messages.

### Overview

Spread Trade Feed is the trade component of the Nasdaq ISE Spread Feed, publishing real-time Complex Strategy Trade Report messages for executed complex orders. It uses the Nasdaq Itch binary protocol over MoldUdp64 multicast.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers.

### Key Characteristics

- **Spread trade reporting** - Real-time complex strategy trade prints for ISE Options
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing
- **ISE Options** - Coverage of Nasdaq ISE listed instruments

