## PhlxOptions MarketDepth: Nasdaq Phlx Options Market Depth

Itch market data feed providing full depth of market for options traded on the Nasdaq Phlx exchange.

### Overview

MarketDepth delivers order-by-order depth information for all options series listed on Phlx. The feed provides individual order add, modify, delete, and execute messages with nanosecond timestamps, enabling subscribers to reconstruct the full Phlx options order book.

The feed uses Itch binary encoding and includes Phlx-specific options reference data messages. MarketDepth provides greater book visibility than Topo at the cost of higher bandwidth.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Full depth** - Order-by-order visibility across all price levels
- **Options-specific** - Series directory with underlying, expiration, strike, and type
- **Nanosecond timestamps** - High-resolution event timing
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
