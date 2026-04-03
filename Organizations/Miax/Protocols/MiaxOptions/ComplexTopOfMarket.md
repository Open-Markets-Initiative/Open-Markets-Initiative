## Miax Options Complex Top Of Market: Mach Market Data

Mach complex top of market feed for multi-leg strategies on Miax Options exchange.

### Overview

Miax Options ComplexTopOfMarket is the Mach market data feed providing real-time best bid and offer quotes for complex multi-leg strategies on the Miax Options exchange. The feed delivers Bbo updates for spreads, straddles, and other complex option combinations using Miax proprietary binary encoding over multicast.

Subscribers receive continuous quote updates for complex strategy instruments, enabling pricing and risk management for multi-leg positions. The feed provides a focused view of complex strategy pricing separate from the simple instrument top of market feed.

### Transport

Udp multicast with sequenced packets and retransmission for gap recovery.

### Key Characteristics

- **Complex strategies** - Best quotes for multi-leg option combinations
- **Options** - Complex instruments on Miax Options exchange
- **Binary multicast** - Proprietary Mach encoding over Udp multicast
- **Strategy pricing** - Spreads, straddles, and other multi-leg structures
