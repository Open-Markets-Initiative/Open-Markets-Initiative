## JnxEquities Itch: Japannext Pts Equities Order By Order Market Data

Itch-based market data feed publishing order by order events for equities traded on the Japannext proprietary trading system.

### Overview

JnxEquities Itch is the market data protocol used by Japannext to distribute real-time order-by-order data for equities traded on the Jnx Pts venue. The feed delivers individual order add, modify, delete, and execution events so that subscribers can reconstruct the complete limit order book for every listed equity throughout the trading day.

The protocol carries reference data, trading status changes, order book events, and trade messages within a single sequenced stream. Messages are framed with SoupBinTcp over Tcp, which provides session authentication, heartbeat monitoring, and sequence-based recovery for subscribers that need to re-establish their connection.

### Transport

Tcp via SoupBinTcp for reliable sequential delivery of Itch messages over a persistent client session with login and heartbeat management.

### Key Characteristics

- **Order-by-order** - Individual order add, modify, delete, and execution events
- **Full book depth** - Complete order book reconstruction from order-level events
- **Equities focused** - Every equity instrument on the Jnx Pts venue
- **SoupBinTcp framed** - Session-authenticated Tcp with heartbeat and sequence recovery
- **Itch encoded** - Fixed-width Itch-style binary messages for low latency processing
- **Reference data** - Security definitions and trading status integrated with the feed

