## IseOptions OrderComboFeed: Nasdaq Ise Options Order Combo Feed

Itch market data feed providing order-by-order depth for complex options strategies on the Nasdaq Ise exchange.

### Overview

OrderComboFeed delivers individual order messages for complex multi-leg options strategies traded on Ise. The feed covers combination orders including spreads, straddles, and other multi-leg structures, providing order add, modify, delete, and execute messages with nanosecond timestamps.

The feed uses Itch binary encoding with complex order-specific message types. Each complex order references its component legs, including the individual options series and ratios that define the strategy.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Complex orders** - Multi-leg strategy order visibility
- **Order-by-order** - Individual order lifecycle messages
- **Strategy definitions** - Leg components with series and ratio references
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
