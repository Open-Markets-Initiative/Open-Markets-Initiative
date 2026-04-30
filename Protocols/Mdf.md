## Mdf: IceFutures Global Markets Multicast Market Data over iMpact

Multicast market data feed publishing real-time order book, trade, and reference data for futures, options, and Otc products traded on the Intercontinental Exchange. Encoded with the iMpact binary message format and distributed over Udp multicast with A and B channel redundancy and per-packet sequence numbers; complementary Tcp replay and snapshot services provide gap recovery.

Ice Mdf is the iMpact-encoded multicast market data feed for the Intercontinental Exchange, delivering real-time order book, trade, and reference data for futures, options, and Otc products across Ice global markets.

### Overview

Ice Mdf (Multicast Data Feed) is the market data feed for the Intercontinental Exchange (Ice), delivering real-time order book, trade, and reference data for futures, options, and Otc products across Ice global markets including Ice Futures Us, Ice Futures Europe, Ice Endex, and Ice Otc. The feed publishes incremental order book updates, trade messages, settlement prices, open interest, and instrument reference data.

Messages are encoded with the iMpact binary format — compact fixed-width fields for low-latency decoding — and distributed over Ip multicast with A and B channel redundancy for resilience. Complementary Tcp replay and snapshot services provide book snapshots for mid-day initialisation and retransmission of messages missed on the multicast feed.

### Transport

Udp multicast for real-time delivery of sequenced iMpact binary messages with A and B channel redundancy and per-packet sequence numbers. Tcp for the Mdf replay and snapshot services used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Ice global markets** - Futures, options, and Otc across Ice venues
- **iMpact encoding** - Compact fixed-width binary message format for low-latency decoding
- **Multicast delivery** - Udp multicast with A and B channel redundancy
- **Full order book** - Incremental refresh with per-order events
- **Settlement and open interest** - End-of-day settlement data in the feed
- **Instrument reference** - Security definitions integrated with the feed
- **Replay service** - Tcp retransmission for gap recovery
- **Snapshot recovery** - Tcp book snapshots for mid-day initialisation

