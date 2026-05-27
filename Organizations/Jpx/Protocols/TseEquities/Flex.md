## TseEquities Flex: Tokyo arrowhead Market by Order tag-stream feed

Tag-stream binary market data feed published by the Tokyo Stock Exchange arrowhead platform. Distributes order-by-order and execution events for cash equities on Tokyo, Nagoya, Fukuoka, and Sapporo exchanges using length-prefixed tags carried over Udp multicast with a Tcp retransmission and snapshot service.

### Overview

FLEX Market by Order is the order-by-order market data feed of the Japan Exchange Group arrowhead trading platform. Each transmission packet starts with a fixed 26 byte packet header carrying multicast group, sequence, reboot, issue, update, packet split, utility flag, and tag count, followed by a sequence of length-prefixed tags. Each tag starts with a one byte Tag Length followed by Tag Data whose first byte identifies the message type.

The Tcp retransmission and snapshot service uses a separate length-prefixed packet format with a Packet Type byte selecting Login Request, Login Result, Message Response, or End of Message. A Message Response packet wraps regular FLEX tags including their packet headers so user-side replay logic can be identical to the multicast feed.

### Transport

Udp multicast for real-time distribution of length-prefixed FLEX tags grouped into packets that share a 26 byte packet header with sequence and reboot counters for gap detection. Tcp request service for retransmission of missed messages and snapshot delivery of the latest order book state by issue and multicast group.

### Key Characteristics

- **Order-by-order** - Full order book reconstruction from individual order events
- **Tag-stream** - Variable length tags with one byte length prefix and one byte type discriminator
- **Tokyo arrowhead** - Cash equities listed on TSE, NSE, FSE, and SSE
- **Big-endian binary** - Big-endian binary numerics with left-aligned ASCII text fields
- **Multicast delivery** - Udp multicast per multicast group with per-issue update sequencing
- **Tcp recovery** - Tcp retransmission and snapshot request service for recovery

