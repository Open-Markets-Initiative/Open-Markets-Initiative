## OdxSecurityToken Pts: Odx Security Token Itch Market Data

Itch-based market data feed publishing real-time order book and trade events for security tokens traded on the Odx proprietary trading system.

### Overview

Odx Security Token Pts Itch is the market data protocol for the Odx security token venue, delivering real-time order-by-order events using the Nasdaq Itch binary protocol for digital security tokens traded on the Odx proprietary trading system.

### Transport

Udp multicast for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers. Tcp via SoupBinTcp for snapshot and retransmission services.

### Key Characteristics

- **Security tokens** - Digital securities on the Odx venue
- **Order-by-order** - Full depth of book from individual order events
- **Itch encoded** - Nasdaq Itch binary message format
- **Multicast delivery** - Udp multicast with sequence numbers
- **SoupBinTcp recovery** - Tcp snapshot and retransmission

