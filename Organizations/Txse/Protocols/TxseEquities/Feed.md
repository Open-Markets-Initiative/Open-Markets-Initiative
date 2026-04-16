## TxseEquities Feed: Txse Binary Market Data

Binary market data feed publishing real-time order book, trade, and session events for equities traded on the Texas Stock Exchange using the Rake framing layer.

### Overview

Feed is the market data protocol for the Texas Stock Exchange (Txse), publishing real-time order book events, trade reports, and session state messages for every equity listed on the venue. The feed is delivered in a sequenced binary format over the Txse Rake framing layer which provides the packet headers, session identification, and sequence numbers used by subscribers to detect gaps.

The protocol carries order add, modify, delete, and execute events along with trade reports, instrument reference data, trading status, and auction messages. Multicast distribution provides low-latency real-time delivery, while a Tcp gap fill and snapshot service built on the Rake session layer gives subscribers a full recovery path for missed multicast messages or mid-day initialisation.

### Transport

Udp multicast via the Txse Rake Udp framing for real-time delivery of sequenced market data messages with per-packet sequence numbers for gap detection. Tcp via the Txse Rake session layer for gap fill and snapshot recovery of messages missed on the multicast feed.

### Key Characteristics

- **Order-by-order** - Full depth of book reconstruction from individual order events
- **Rake framing** - Runs on top of the Txse session and framing transport
- **Multicast delivery** - Real-time Udp multicast distribution with sequence numbers
- **Snapshot and gap fill** - Tcp recovery services over the Rake session layer
- **Trade reports** - Last sale messages published alongside the order book
- **Reference data** - Instrument definitions and trading status integrated with the feed
- **Equities focused** - Every equity listed on the Texas Stock Exchange

