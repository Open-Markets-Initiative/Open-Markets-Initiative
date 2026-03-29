## Miax Options Top Of Market: Mach Market Data

Mach top of market feed for Miax Options exchange.

### Overview

Miax Options TopOfMarket is the Mach market data feed providing real-time best bid and offer quotes and trade information for options listed on the Miax Options exchange. The feed delivers Bbo updates with associated sizes and last sale data using Miax proprietary binary encoding over multicast.

Subscribers receive continuous quote updates reflecting the current best prices available on Miax Options. The feed provides a lightweight view of market pricing suitable for quoting, pricing, and surveillance applications without full depth of book overhead.

### Transport

Udp multicast with sequenced packets and retransmission for gap recovery.

### Key Characteristics

- **Top of market** - Best bid and offer quotes with sizes
- **Options** - Covers all options listed on Miax Options
- **Binary multicast** - Proprietary Mach encoding over Udp multicast
- **Trade data** - Last sale information with trade conditions
