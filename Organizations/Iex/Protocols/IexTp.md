## IexTp: Iex Transport Protocol

Transport protocol providing sequenced Udp multicast delivery with retransmission support for Iex market data feeds.

### Overview

IexTp is the Iex Transport Protocol used as the underlying delivery mechanism for all Iex market data feeds including Deep and Tops. The protocol defines a segment-based framing structure over Udp multicast, where each segment contains a header with version, message protocol identifier, channel identifier, session identifier, sequence number, message count, and payload length. This structure enables receivers to detect gaps, identify sessions, and parse enclosed application messages.

IexTp supports retransmission requests for recovering missed segments. When a receiver detects a sequence gap, it can request retransmission of specific segments to fill the gap without waiting for a full snapshot recovery cycle. The protocol is designed for efficient multicast delivery of exchange data with the reliability features needed for market data applications.

### Transport

Udp multicast. IexTp segments are carried as Udp datagrams to multicast group addresses. Each segment is self-describing with a fixed header containing session, sequence, and payload metadata. Retransmission is available via a separate request mechanism for gap recovery.

### Key Characteristics

- **Segment-based framing** - Fixed header with session, sequence, and message count fields
- **Udp multicast delivery** - Efficient one-to-many distribution over multicast groups
- **Sequence numbered** - Every segment carries a sequence number for gap detection
- **Retransmission support** - Receivers can request retransmission of missed segments
- **Session identification** - Session identifiers distinguish between feed restarts
- **Multi-message segments** - Each segment can carry multiple application messages
