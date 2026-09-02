## Mtbt: Multicast Tick By Tick

Nse's tick by tick market data feed, disseminating every order entry, modification, and cancellation together with each resulting trade on a real time basis. Contracts are distributed across multiple multicast streams, each carrying its own sequence number space, with a Tcp recovery service for replaying missed ticks.

### Overview

Mtbt is an order by order feed rather than an aggregated depth feed. Every new order, modification, and cancellation is published with a day unique Order Id, and clients rebuild the book by tracking those identifiers. Old price and quantity are not carried on modification or cancellation messages, so a client must retain the previous image of each order to apply an update.

Contracts are identified only by a numeric Token. The mapping from Token to symbol, instrument, expiry, and strike is published separately as an end of day plain text contract information file, which also records which stream carries each contract. A client must load that file before processing the feed.

Packets are little endian and packed to a one byte boundary. Each packet carries a fixed eight byte stream header followed by a single message whose first byte identifies the message type.

### Transport

Real time multicast, one stream per contract group, with a per stream sequence number that restarts at 1 each trading day and after a disaster recovery switchover. Recovery server replaying a requested sequence range of missed ticks for a single stream.

### Key Characteristics

- **Order by order** - Every order entry, modification, and cancellation is published individually
- **Token addressed** - Contracts are referenced by numeric Token resolved through a separate masters file
- **Streamed** - Contracts are partitioned across multicast streams with independent sequence numbers
- **Nanosecond timestamps** - Message times are nanoseconds since 01-Jan-1980 00:00:00
- **Little endian** - Fixed width fields, byte packed, little endian on the wire
- **Tcp recovery** - Missed sequence ranges are replayed on request by a load balanced recovery server

