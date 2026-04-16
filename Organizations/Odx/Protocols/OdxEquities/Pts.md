## OdxEquities Pts: Odx Equities Itch Market Data

Itch-based market data feed publishing real-time order book and trade events for equities traded on the Odx proprietary trading system.

### Overview

Odx Equities Pts Itch is the market data protocol for the Odx equities venue, delivering real-time order-by-order events using the Nasdaq Itch binary protocol. The feed publishes order add, modify, delete, and trade messages for securities listed on the Odx proprietary trading system.

### Transport

Udp multicast for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp for snapshot and retransmission services.

### Key Characteristics

- **Order-by-order** - Full depth of book from individual order events
- **Odx equities venue** - Proprietary trading system
- **Itch encoded** - Nasdaq Itch binary message format
- **Multicast delivery** - Udp multicast with sequence numbers
- **SoupBinTcp recovery** - Tcp snapshot and retransmission

