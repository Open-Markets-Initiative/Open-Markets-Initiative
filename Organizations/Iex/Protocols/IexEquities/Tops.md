## IexEquities Tops: Iex Equities Top Of Book Quotations And Trade Data

Real-time top of book feed publishing best bid and offer quotations and last sale trade messages for Nms securities traded on the Investors Exchange.

### Overview

Iex Tops is the top of book market data product for the Investors Exchange, publishing the best bid and best offer along with last sale trade information for every Nms security traded on the exchange. The feed is designed for subscribers who need current quotations without the overhead of a full depth of book feed.

Tops is carried over the Iex Transport Protocol (IexTp), which provides the packet framing, per-packet sequence numbers, and replay service used across all Iex market data products. Subscribers receive quote update, trade report, trading status, operational halt, and short sale price test messages as fixed-width binary messages packed into multicast datagrams.

Tops Snap augments the Tops gap-fill retransmission service with a separate snapshot protocol. Applications buffer the Tops multicast, connect to a Tops Snap server, and issue a Snapshot Request. A successful response is a Snapshot Start message, a stream of Snapshot Data messages each wrapping one complete Tops feed message with its IexTp header, and a Snapshot End message carrying the sequence number at which the snapshot was created.

On receipt of a Snapshot Response, applications initialize their price level books from the snapshot, apply any buffered real-time updates with higher sequence numbers, disconnect from the snapshot server, and continue processing the Tops multicast as normal. The protocol has no unsolicited messages; connections idle for a significant period may be disconnected by either side.

### Transport

Udp multicast carried over the Iex Transport Protocol for real-time delivery of quote update and trade report messages with sequence-number gap detection. Tcp to the Iex replay service for recovery of messages missed on the multicast feed, shared with the Deep and Deep Plus market data products. Tcp request-response to the Tops Snap server, length-framed snapshot messages wrapping complete Tops feed messages with their IexTp headers.

### Key Characteristics

- **Top of book** - Best bid and best offer for every Iex-listed security
- **Last sale trades** - Trade report messages with price, size, and conditions
- **IexTp transport** - Packet framing and recovery provided by the Iex Transport Protocol
- **Multicast delivery** - Real-time Udp multicast distribution of Tops messages
- **Replay service** - Tcp sequence-range re-request for gap recovery
- **Trading status** - Operational halt and short sale price test notifications
- **Binary encoded** - Fixed-width Iex message format for low latency processing
- **Request response** - Client-initiated snapshot requests with no unsolicited messages
- **Point-in-time snapshot** - Price level and trading status state for all Iex symbols at a single sequence number
- **Wrapped feed messages** - Snapshot Data messages carry complete Tops feed messages with their IexTp headers
- **Late-start recovery** - Accelerates recovery without replaying the full day of multicast data
- **Authenticated** - Token-based authentication with daily request quotas
- **Tcp delivery** - Length-framed binary messages over a Tcp connection

