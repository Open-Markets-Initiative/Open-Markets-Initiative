## NomOptions Itto: Nasdaq Options Market Order Feed

Itch market data feed providing full depth of book for options traded on the Nasdaq Options Market.

### Overview

Itto is the primary Nom market data feed, delivering order-by-order depth information for all options series listed on the Nasdaq Options Market. The feed provides individual order add, modify, delete, and execute messages with nanosecond timestamps, enabling complete order book reconstruction.

The feed uses Itch binary encoding with Nom-specific message types and includes options series directory, trading action, and system event reference data. Itto supports both simple options and complex strategy visibility.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Full depth of book** - Order-by-order visibility across all price levels
- **Options-specific** - Series directory with underlying, expiration, strike, and type
- **Nanosecond timestamps** - High-resolution event timing
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
