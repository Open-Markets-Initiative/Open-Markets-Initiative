## Mtbt Ndal: Multicast Tick By Tick Data Feed

The tick by tick market data feed as published by Nse Data and Analytics Limited to data subscribers, distinct from the Mtbt specification issued to Non Neat Front End members. The wire encoding is the same little endian Binary one, but the two documents are separate publications with independent version numbers and different message sets: this one covers the Capital Market and Currency Derivatives segments and folds each order action into a single Order structure, where the members' document splits them and adds the Futures and Options and Commodity segments.

### Overview

This is the Non-Confidential publication, titled "NDAL MTBT Specification" and issued by Nse Data and Analytics Limited. The members' Mtbt document is marked Confidential and is versioned separately, so a version number alone does not identify which of the two a spec came from.

The message set is the same ten message types on the wire, but this document presents the three order actions as one Order Message with a Message Type of N, M, or X, and the three spread order actions as one Spread Order Message with G, H, or J.

Spread contracts and the spread messages are documented for the Currency Derivatives segment only.

### Transport

Real time multicast, a separate channel per stream, carrying the sequenced data messages. Recovery server replaying a requested sequence range of missed ticks for a single stream.

### Key Characteristics

- **Order by order** - Every order entry, modification, and cancellation is published individually
- **Token addressed** - Contracts are referenced by numeric Token resolved through a separate contract information file
- **Streamed** - Contracts are partitioned across multicast streams with independent sequence numbers
- **Nanosecond timestamps** - Message times are nanoseconds since 01-Jan-1980 00:00:00
- **Little endian** - Fixed width fields, byte packed, little endian on the wire
- **Tcp recovery** - Missed sequence ranges are replayed on request by the recovery server

