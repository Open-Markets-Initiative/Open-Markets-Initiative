## Index Gids: Nasdaq Global Index Data Service 2.0

Itch-based market data feed publishing index and exchange traded product reference data, intraday values, settlement values and summaries for Nasdaq and third party indexes.

### Overview

The Global Index Data Service 2.0 is powered by Nasdaq INET technology and uses the Itch messaging standard. Index messages carry the index directory, issue symbol participation, intraday index values, settlement values and equity, fixed income and commodity index summaries; exchange traded product messages carry the directory and daily valuation, intraday values and summaries.

Numeric fields are signed big-endian binary numbers, with long values carrying an implied decimal precision of up to eleven places. Timestamps are split between a standalone seconds message giving the seconds since the Unix epoch in UTC and a nanosecond offset carried in each message. Nasdaq delivers the feed over MoldUdp64 and, since April 2020, by cloud delivery.

### Transport

Udp multicast via MoldUdp64 for delivery of sequenced Itch messages, with a rerequest service for missed messages.

### Key Characteristics

- **Index values** - Intraday, settlement and summary values for Nasdaq and third party indexes
- **Exchange traded products** - Directory, daily valuation, intraday value and summary messages
- **Nasdaq Itch** - Sequenced binary messages, variable in length by message type
- **MoldUdp64** - Packaged over the Nasdaq MoldUdp64 multicast framing
- **Split timestamps** - Seconds message plus a nanosecond offset in each message

