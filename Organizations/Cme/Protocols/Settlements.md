## Settlements: Cme Settlement Price Data

Sbe-encoded market data feed providing settlement prices, cleared volume, and open interest for Cme Group futures and options.

### Overview

The Cme Settlements feed delivers settlement-specific market data including final and preliminary settlement prices, actual and theoretical values, cleared volume, open interest, and high/low price data. Settlement prices are categorized by type using a bitfield indicating whether the price is final or preliminary, actual or theoretical, rounded or unrounded, intraday, or cabinet.

The protocol uses Sbe encoding with Fix 5.0 Sp2 semantics. Messages include MdIncrementalRefreshSettle with fields for product identification, pricing, and settlement metadata. Cycle flags distinguish between estimated and actual adjusted values.

### Transport

Udp multicast with Sbe-encoded messages. Same packet structure as Mdp 3.0 feeds.

### Key Characteristics

- **Sbe encoded** - Fixed-position, fixed-length fields with little-endian byte ordering
- **Settlement price types** - Bitfield for final/preliminary, actual/theoretical, rounded/unrounded, intraday, and cabinet
- **Cycle flags** - Estimated vs actual adjusted values
- **High-precision pricing** - PriceNull9 composite with 10^-9 exponent
- **Nanosecond timestamps** - Transaction time in nanoseconds since Unix epoch
