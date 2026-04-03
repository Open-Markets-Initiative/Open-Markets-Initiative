## BxOptions DepthOfMarket: Nasdaq Bx Options Depth Of Market

Itch market data feed providing full depth of market for options traded on the Nasdaq Bx Options exchange.

### Overview

DepthOfMarket delivers order-by-order depth information for all options series listed on Bx Options. The feed provides individual order add, modify, delete, and execute messages with nanosecond timestamps, enabling subscribers to reconstruct the full options order book.

The feed uses Itch binary encoding and includes options-specific reference data messages for series directory, trading action, and system events. Each options series is identified by its underlying symbol, expiration, strike, and option type.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Full depth** - Order-by-order visibility across all price levels
- **Options-specific** - Series directory with underlying, expiration, strike, and type
- **Nanosecond timestamps** - High-resolution event timing
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
