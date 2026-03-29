## IseOptions OrderFeed: Nasdaq Ise Options Order Feed

Itch market data feed providing order-by-order depth for options traded on the Nasdaq Ise exchange.

### Overview

OrderFeed delivers individual order add, modify, delete, and execute messages for all options series on Ise. The feed provides full depth of book visibility with nanosecond timestamps, enabling complete order book reconstruction.

The feed uses Itch binary encoding with Ise-specific message types and includes options series directory, trading action, and system event reference data messages.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Order-by-order** - Individual order lifecycle messages for full book depth
- **Options-specific** - Series directory with underlying, expiration, strike, and type
- **Nanosecond timestamps** - High-resolution event timing
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
