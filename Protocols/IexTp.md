## IEX-TP: IEX Transport Protocol

Custom transport protocol developed by IEX Exchange for sequenced delivery of market data feeds including DEEP (full depth of book) and TOPS (top of book) over UDP multicast, with TCP and UDP unicast retransmission for gap recovery.

### Overview

The IEX Transport Protocol (IEX-TP) is the lower-level transport layer used by IEX Exchange (Investors Exchange) to disseminate its proprietary market data feeds. IEX-TP provides a lightweight framing and sequencing mechanism built on top of UDP, enabling ordered and recoverable delivery of market data messages without the overhead of a full TCP session for each subscriber.

DEEP is IEX's full depth of book and last sale feed, providing order-by-order visibility into the IEX order book along with trade reports, auction information, and administrative messages. TOPS is a lighter-weight feed delivering top-of-book quotes and last sale information. Both feeds use IEX-TP as their transport layer, with the protocol handling sequencing, session management, and gap detection while the application-layer specification defines the individual message types.

IEX-TP segments are delivered via UDP multicast for primary distribution. Each segment carries a header containing protocol version, message protocol identifier (distinguishing DEEP from TOPS), channel identifier, session identifier, payload length, message count, stream byte offset, first message sequence number, and send timestamp. For recovery, IEX-TP supports both TCP and UDP unicast retransmission where clients request specific missed segments by sequence number.

### Transport

IEX-TP uses UDP multicast as its primary delivery mechanism. Each segment consists of a fixed-length header followed by a payload containing one or more application-level messages. Messages within a segment are implicitly numbered sequentially starting from the first message sequence number in the header. The stream byte offset provides a cumulative byte counter across all segments for byte-level tracking. For gap recovery, both TCP and UDP unicast retransmission are supported. Sessions are uniquely identified by session ID with independent sequence number spaces.

### Key Characteristics

- **UDP multicast primary delivery** - Market data distributed via multicast for efficient one-to-many dissemination
- **Sequenced segments** - Each segment carries a first message sequence number with implicit sequential numbering
- **Stream byte offset** - Cumulative byte counter enabling byte-level stream position tracking
- **Dual retransmission modes** - Gap recovery available via both TCP and UDP unicast
- **Session-scoped sequencing** - Each session has an independent sequence number space identified by session ID
- **Lightweight framing** - Minimal header overhead with fixed-length fields for fast parsing
- **Multi-feed support** - Message protocol identifier distinguishes different application feeds (DEEP, TOPS)
