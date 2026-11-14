## C1Options Index: Cboe Streaming Market Index (CSMI)

Legacy Cboe streaming market data feed publishing calculated index values, with bid and ask index values where they are calculated.

### Overview

Cboe Streaming Market Index (CSMI) is the legacy Cboe feed for index values. Each Index Value message carries an index symbol and market data entries for its index value and, for indices where they are calculated, its bid and ask values. From February 2018 the feed was split across CSMI, MSCI, FTSE, cryptocurrency and INAV data channels.

### Transport

Udp multicast in a primary and secondary group pair per channel, one way only with no mechanism for retransmission.

### Key Characteristics

- **Legacy format** - Cboe Streaming Market (Csm) templates with big endian binary fields
- **Index values** - Index value, bid and ask entries per calculated index
- **Multicast delivery** - Primary and secondary multicast groups per channel
- **No retransmission** - A gap leaves the channel's indexes suspect until their next index value message

