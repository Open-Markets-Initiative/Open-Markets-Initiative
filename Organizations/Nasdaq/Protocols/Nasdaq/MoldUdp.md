## Mold Udp: Nasdaq Reliable Multicast Transport Layer

Packet-level framing and sequencing transport used across Nasdaq multicast market data feeds providing session identification, packet sequencing, and gap detection.

### Overview

MoldUdp64 is the Nasdaq reliable multicast transport layer used by Itch, Ouch, and other Nasdaq market data protocols. It defines the packet header with session identifier, starting sequence number, message count, and message block format used to pack one or more application-level messages into each Udp multicast datagram.

### Transport

Udp multicast carrying Mold Udp 64 packets with session identifier, starting sequence number, message count, and per-message payloads.

### Key Characteristics

- **Packet framing** - Session, sequence, and message count headers
- **Message block** - One or more application messages per datagram
- **Gap detection** - Sequence numbers allow subscribers to identify missed packets
- **Shared layer** - Used by Itch, Ouch, and other Nasdaq feeds
- **Udp multicast** - Efficient one-to-many delivery

