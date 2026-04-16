## Nets: Nsx Australia Equities Market Data

Itch-based market data feed publishing real-time order book and trade events for equities traded on the National Stock Exchange of Australia.

### Overview

Nets Itch is the market data protocol for the National Stock Exchange of Australia (Nsx), delivering real-time order-by-order events for equities listed on the Nsx venue. The feed publishes order add, modify, delete, and trade messages using the Nasdaq Itch binary protocol.

### Transport

Udp multicast for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp to the snapshot and retransmission services for recovery of missed multicast messages.

### Key Characteristics

- **Order-by-order** - Full depth of book from individual order events
- **Nsx Australia** - National Stock Exchange of Australia
- **Itch encoded** - Nasdaq Itch binary message format
- **Multicast delivery** - Udp multicast with sequence numbers
- **SoupBinTcp recovery** - Tcp snapshot and retransmission

