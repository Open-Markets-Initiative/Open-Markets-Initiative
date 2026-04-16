## i Mpact: Ice iMpact Global Markets Multicast Market Data

Binary multicast market data feed publishing real-time order book, trade, and reference data for futures, options, and Otc products traded on the Intercontinental Exchange.

### Overview

Ice iMpact is the multicast market data feed for the Intercontinental Exchange (Ice), delivering real-time order book, trade, and reference data for futures, options, and Otc products across Ice global markets including Ice Futures Us, Ice Futures Europe, Ice Endex, and Ice Otc. The feed publishes incremental order book updates, trade messages, settlement prices, open interest, and instrument reference data.

Messages are distributed over Ip multicast with A and B channel redundancy for resilience, using the Ice iMpact binary message format with compact fixed-width fields for low-latency decoding. Complementary Tcp replay and snapshot services provide book snapshots for mid-day initialisation and retransmission of messages missed on the multicast feed.

### Transport

Udp multicast for real-time delivery of sequenced Ice iMpact binary messages with A and B channel redundancy and per-packet sequence numbers. Tcp for the Ice iMpact replay and snapshot services used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Ice global markets** - Futures, options, and Otc across Ice venues
- **Multicast delivery** - Udp multicast with A and B channel redundancy
- **Full order book** - Incremental refresh with per-order events
- **Settlement and open interest** - End-of-day settlement data in the feed
- **Instrument reference** - Security definitions integrated with the feed
- **Replay service** - Tcp retransmission for gap recovery
- **Snapshot recovery** - Tcp book snapshots for mid-day initialisation

