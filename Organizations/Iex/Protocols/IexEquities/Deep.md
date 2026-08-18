## IexEquities Deep: Iex Equities Aggregated Depth Of Book Data

Aggregated price-level depth of book feed publishing visible order book state and trade messages for Nms securities traded on the Investors Exchange.

### Overview

Iex Deep is the aggregated depth of book market data product for the Investors Exchange, publishing price-level order book state for every Nms security traded on the exchange. The feed delivers price-level updates, trade reports, and auction information events that allow subscribers to maintain a full aggregated depth view without processing individual order events.

Deep is carried over the Iex Transport Protocol (IexTp) which provides the packet framing, per-packet sequence numbers, and replay service used across all Iex market data products. Subscribers receive price-level add, update, and delete messages, trade reports, auction collar and indicative price messages, trading status changes, and short sale price test events as fixed-width binary messages.

Deep Snap augments the Deep gap-fill retransmission service with a separate snapshot protocol. Applications buffer the Deep multicast, connect to a Deep Snap server, and issue a Snapshot Request. A successful response is a Snapshot Start message, a stream of Snapshot Data messages each wrapping one complete Deep feed message with its IexTp header, and a Snapshot End message carrying the sequence number at which the snapshot was created.

On receipt of a Snapshot Response, applications initialize their price level books from the snapshot, apply any buffered real-time updates with higher sequence numbers, disconnect from the snapshot server, and continue processing the Deep multicast as normal. The protocol has no unsolicited messages; connections idle for a significant period may be disconnected by either side.

### Transport

Udp multicast carried over the Iex Transport Protocol for real-time delivery of price-level depth updates, trade reports, and auction messages. Tcp to the Iex replay service for recovery of messages missed on the multicast feed, shared with the Tops and Deep Plus market data products. Tcp request-response to the Deep Snap server, length-framed snapshot messages wrapping complete Deep feed messages with their IexTp headers.

### Key Characteristics

- **Aggregated depth** - Price-level book state rather than individual orders
- **Trade reports** - Last sale trade messages published alongside book updates
- **Auction events** - Auction collar, indicative price, and book clearing events
- **IexTp transport** - Packet framing and recovery via the Iex Transport Protocol
- **Multicast delivery** - Real-time Udp multicast distribution of Deep messages
- **Replay service** - Tcp sequence-range re-request for gap recovery
- **Trading status** - Operational halts and short sale price test notifications
- **Binary encoded** - Fixed-width Iex message format for low latency processing
- **Request response** - Client-initiated snapshot requests with no unsolicited messages
- **Point-in-time snapshot** - Price level and trading status state for all Iex symbols at a single sequence number
- **Wrapped feed messages** - Snapshot Data messages carry complete Deep feed messages with their IexTp headers
- **Late-start recovery** - Accelerates recovery without replaying the full day of multicast data
- **Authenticated** - Token-based authentication with daily request quotas
- **Tcp delivery** - Length-framed binary messages over a Tcp connection

