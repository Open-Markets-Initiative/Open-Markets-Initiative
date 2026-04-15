## IexEquities Iex Tp: Iex Transport Layer For Market Data Feeds

Lightweight transport protocol providing sequenced message framing and gap recovery for all Iex real-time market data feeds including Tops, Deep, and Deep Plus.

### Overview

Iex Transport Protocol (IexTp) is the framing and recovery layer used by all Iex real-time market data feeds. It defines the packet header with session identifier, first message sequence number, message count, and timestamp, along with the message block format used to pack one or more application-level messages into a single datagram.

The transport supports two delivery modes. Live market data is distributed over Udp multicast for low-latency fanout, with per-packet sequence numbers enabling subscribers to detect gaps and request replay. A companion Tcp replay service lets clients re-request specific sequence ranges after a gap, providing a complete reliability path without coupling it to any particular application-level feed.

### Transport

Udp multicast carrying IexTp packets with session, sequence, and message-count headers that frame one or more application-level messages per datagram. Tcp to the Iex replay service for recovery of messages lost on the multicast feed, with session-based authentication and sequence-number requests.

### Key Characteristics

- **Transport layer** - Framing and recovery for all Iex market data feeds
- **Packet framing** - Session, sequence, message count, and timestamp headers
- **Message block** - One or more application messages per datagram
- **Multicast delivery** - Real-time Udp multicast distribution of live data
- **Replay service** - Tcp sequence-range re-request for gap recovery
- **Shared layer** - Used by Tops, Deep, Deep Plus, and other Iex feeds

