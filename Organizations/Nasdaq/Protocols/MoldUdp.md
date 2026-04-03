## MoldUdp: Nasdaq Multicast Transport

Udp multicast session and sequencing protocol providing reliable ordered delivery for Nasdaq market data feeds.

### Overview

MoldUdp is the Nasdaq transport protocol for delivering sequenced market data over Udp multicast. The protocol provides a lightweight framing layer that adds session identification, sequence numbering, and message count fields to multicast packets, enabling receivers to detect gaps and request retransmission of missed messages. MoldUdp64 extends the original MoldUdp with 64-bit sequence numbers to support higher message volumes.

The protocol defines a downstream session identified by a 10-character session identifier and a monotonically increasing sequence number. Each Udp packet carries the session identifier, the sequence number of the first message in the packet, and a message count indicating how many messages are contained. Receivers track the next expected sequence number and can detect gaps by comparing incoming packet sequence numbers.

### Transport

Udp multicast for primary data delivery. Retransmission requests are sent via Tcp or Udp to dedicated request servers for gap recovery. MoldUdp and MoldUdp64 variants differ in sequence number field width.

### Key Characteristics

- **Udp multicast** - Efficient one-to-many delivery for market data
- **Sequenced delivery** - Monotonically increasing sequence numbers for gap detection
- **MoldUdp64** - Extended variant with 64-bit sequence numbers for high-volume feeds
- **Session identification** - 10-character session identifiers for stream distinction
- **Retransmission support** - Gap recovery via dedicated retransmission request servers
- **Message aggregation** - Multiple messages packed into single Udp packets
