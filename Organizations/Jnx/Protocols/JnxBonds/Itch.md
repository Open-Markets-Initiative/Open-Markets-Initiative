## JnxBonds Itch: Japannext Pts Bonds Order By Order Market Data

Itch-based market data feed publishing order by order events for bonds traded on the Japannext Jnx Pts bonds venue.

### Overview

JnxBonds Itch is the market data protocol used by Japannext to distribute real-time order-by-order data for bonds traded on the Jnx Pts bonds venue. The feed delivers individual order add, modify, delete, and execution events enabling subscribers to reconstruct the complete order book for every listed bond throughout the trading day.

The protocol shares its architecture with JnxEquities Itch: a sequenced Itch-style message stream framed with SoupBinTcp over Tcp, providing session authentication, heartbeat monitoring, and sequence-based recovery. Reference data, trading status, order book events, and trade messages are all carried within the same stream.

### Transport

Tcp via SoupBinTcp for reliable sequential delivery of Itch messages over a persistent client session with login and heartbeat management.

### Key Characteristics

- **Order-by-order** - Individual order add, modify, delete, and execution events
- **Full book depth** - Complete order book reconstruction from order-level events
- **Bonds focused** - Every bond instrument on the Jnx Pts bonds venue
- **SoupBinTcp framed** - Session-authenticated Tcp with heartbeat and sequence recovery
- **Itch encoded** - Fixed-width Itch-style binary messages for low latency processing
- **Reference data** - Security definitions and trading status integrated with the feed

