## IexEquities Tops: Iex Equities Top Of Book Quotations And Trade Data

Real-time top of book feed publishing best bid and offer quotations and last sale trade messages for Nms securities traded on the Investors Exchange.

### Overview

Iex Tops is the top of book market data product for the Investors Exchange, publishing the best bid and best offer along with last sale trade information for every Nms security traded on the exchange. The feed is designed for subscribers who need current quotations without the overhead of a full depth of book feed.

Tops is carried over the Iex Transport Protocol (IexTp), which provides the packet framing, per-packet sequence numbers, and replay service used across all Iex market data products. Subscribers receive quote update, trade report, trading status, operational halt, and short sale price test messages as fixed-width binary messages packed into multicast datagrams.

### Transport

Udp multicast carried over the Iex Transport Protocol for real-time delivery of quote update and trade report messages with sequence-number gap detection. Tcp to the Iex replay service for recovery of messages missed on the multicast feed, shared with the Deep and Deep Plus market data products.

### Key Characteristics

- **Top of book** - Best bid and best offer for every Iex-listed security
- **Last sale trades** - Trade report messages with price, size, and conditions
- **IexTp transport** - Packet framing and recovery provided by the Iex Transport Protocol
- **Multicast delivery** - Real-time Udp multicast distribution of Tops messages
- **Replay service** - Tcp sequence-range re-request for gap recovery
- **Trading status** - Operational halt and short sale price test notifications
- **Binary encoded** - Fixed-width Iex message format for low latency processing

