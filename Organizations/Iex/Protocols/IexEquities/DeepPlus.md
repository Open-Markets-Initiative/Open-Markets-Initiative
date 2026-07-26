## IexEquities Deep Plus: Iex Equities Order By Order Depth Of Book Data

Order-by-order depth of book feed publishing individual displayed orders, trades, and auction messages for Nms securities traded on the Investors Exchange.

### Overview

Iex Deep Plus (DEEP+) is the order-by-order depth of book market data product for the Investors Exchange, publishing individual displayed order events for every Nms security traded on the exchange. Where Deep aggregates displayed interest by price level, Deep Plus delivers add, revise, and delete events for each displayed order so subscribers can maintain a full order-level view of the book.

Deep Plus is carried over the Iex Transport Protocol (IexTp) which provides the packet framing, per-packet sequence numbers, and replay service used across all Iex market data products. Alongside order events the feed carries trade reports, auction information, trading status changes, and short sale price test events as fixed-width binary messages.

### Transport

Udp multicast carried over the Iex Transport Protocol for real-time delivery of individual order events, trade reports, and auction messages. Tcp to the Iex replay service for recovery of messages missed on the multicast feed, shared with the Tops and Deep market data products.

### Key Characteristics

- **Order by order** - Individual displayed order events rather than aggregated price levels
- **Trade reports** - Last sale trade messages published alongside order events
- **Auction events** - Auction collar, indicative price, and book clearing events
- **IexTp transport** - Packet framing and recovery via the Iex Transport Protocol
- **Multicast delivery** - Real-time Udp multicast distribution of Deep Plus messages
- **Replay service** - Tcp sequence-range re-request for gap recovery
- **Trading status** - Operational halts and short sale price test notifications
- **Binary encoded** - Fixed-width Iex message format for low latency processing

