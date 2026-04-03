## Onyx Futures Top Of Market: Mach Market Data

Mach top of market feed for Miax Onyx Futures exchange.

### Overview

Onyx Futures TopOfMarket is the Mach market data feed providing real-time best bid and offer quotes and trade information for futures listed on the Miax Onyx Futures exchange. The feed delivers Bbo updates with associated sizes and last sale data using Miax proprietary binary encoding over multicast.

Subscribers receive continuous quote updates reflecting the current best prices available on Onyx Futures. The feed provides a lightweight view of futures market pricing suitable for quoting, pricing, and surveillance applications.

### Transport

Udp multicast with sequenced packets and retransmission for gap recovery.

### Key Characteristics

- **Top of market** - Best bid and offer quotes with sizes
- **Futures** - Covers all futures listed on Miax Onyx Futures
- **Binary multicast** - Proprietary Mach encoding over Udp multicast
- **Trade data** - Last sale information with trade conditions
