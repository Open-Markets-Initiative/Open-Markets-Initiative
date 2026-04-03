## Onyx Futures Depth Of Market: Mach Market Data

Mach depth of market feed for Miax Onyx Futures exchange.

### Overview

Onyx Futures DepthOfMarket is the Mach market data feed providing full price level depth for futures listed on the Miax Onyx Futures exchange. The feed delivers depth updates across all visible price levels, enabling subscribers to reconstruct the complete order book using Miax proprietary binary encoding over multicast.

Subscribers receive continuous depth updates reflecting the current state of the Onyx Futures order book. The feed provides full depth of book visibility for pricing, execution, and market making applications requiring more detail than top of market alone.

### Transport

Udp multicast with sequenced packets and retransmission for gap recovery.

### Key Characteristics

- **Full depth** - Price level depth across all visible levels
- **Futures** - Covers all futures listed on Miax Onyx Futures
- **Binary multicast** - Proprietary Mach encoding over Udp multicast
- **Book reconstruction** - Complete order book state from depth messages
