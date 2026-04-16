## IexEquities Deep: Iex Equities Aggregated Depth Of Book Data

Aggregated price-level depth of book feed publishing visible order book state and trade messages for Nms securities traded on the Investors Exchange.

### Overview

Iex Deep is the aggregated depth of book market data product for the Investors Exchange, publishing price-level order book state for every Nms security traded on the exchange. The feed delivers price-level updates, trade reports, and auction information events that allow subscribers to maintain a full aggregated depth view without processing individual order events.

Deep is carried over the Iex Transport Protocol (IexTp) which provides the packet framing, per-packet sequence numbers, and replay service used across all Iex market data products. Subscribers receive price-level add, update, and delete messages, trade reports, auction collar and indicative price messages, trading status changes, and short sale price test events as fixed-width binary messages.

### Transport

Udp multicast carried over the Iex Transport Protocol for real-time delivery of price-level depth updates, trade reports, and auction messages. Tcp to the Iex replay service for recovery of messages missed on the multicast feed, shared with the Tops and Deep Plus market data products.

### Key Characteristics

- **Aggregated depth** - Price-level book state rather than individual orders
- **Trade reports** - Last sale trade messages published alongside book updates
- **Auction events** - Auction collar, indicative price, and book clearing events
- **IexTp transport** - Packet framing and recovery via the Iex Transport Protocol
- **Multicast delivery** - Real-time Udp multicast distribution of Deep messages
- **Replay service** - Tcp sequence-range re-request for gap recovery
- **Trading status** - Operational halts and short sale price test notifications
- **Binary encoded** - Fixed-width Iex message format for low latency processing

