## Glimpse: Point in time order book snapshot service

Nasdaq Glimpse a request response snapshot service delivering the current state of the order book over SoupBinTcp so a subscriber joining mid session can build its book before applying the live Itch multicast stream.

### Overview

Glimpse solves the late joiner problem. Itch multicast carries only incremental order events, so a subscriber starting mid session has no way to know the book state that accumulated before it connected. Glimpse hands over that accumulated state in one pass, ending with the sequence number the live stream should be resumed from.

The message bodies reuse the Itch message formats of the feed being snapshotted, which is why a Glimpse specification tracks its Itch sibling version for version. What differs is the session layer and the delivery model rather than the encoding of the individual messages, so the two are paired as separate encodings of one protocol.

Developed by Nasdaq alongside Itch and licensed to other venues, so a Glimpse service appears wherever the Nasdaq market data stack is deployed. Borsa Istanbul runs one over Genium Inet in addition to the Nasdaq US equities and options markets.

### Transport

Glimpse is delivered over SoupBinTcp rather than multicast. A subscriber logs in, receives a snapshot of the book as a sequence of Itch style messages, and is given the sequence number the live feed should be resumed from.

### Key Characteristics

- **Point in time snapshot** - Delivers the order book as it stands when the request is served
- **Request response** - A subscriber logs in and receives one snapshot rather than a continuous stream
- **SoupBinTcp session** - Carried over a reliable Tcp session rather than multicast Udp
- **Itch message bodies** - Reuses the message formats of the feed it snapshots
- **Resume sequence** - Ends with the sequence number the live feed should be joined from

