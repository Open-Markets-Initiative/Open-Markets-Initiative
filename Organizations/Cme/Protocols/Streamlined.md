## Streamlined: Cme Streamlined Market Data

Sbe-encoded market data feed providing streamlined settlement, volume, open interest, and trade data for Cme Group futures and options products.

### Overview

The Cme Streamlined market data feed delivers a focused subset of market data including settlement prices, cleared volume, open interest, and trade information. Unlike Mdp 3.0 which provides full real-time depth of book, Streamlined publishes aggregated and derived data primarily used for end-of-day processing, risk management, and reference data consumption.

The protocol uses Sbe encoding with Fix 5.0 Sp2 semantics and supports incremental refresh messages for settlement data with fields including product Guid, settlement price, volume, open interest, and associated metadata. Messages carry nanosecond-precision timestamps.

### Transport

Udp multicast with Sbe-encoded messages. Same dual-feed architecture and packet structure as Mdp 3.0.

### Key Characteristics

- **Sbe encoded** - Fixed-position, fixed-length fields with little-endian byte ordering
- **Settlement focused** - Settlement prices, cleared volume, open interest, and trade data
- **Incremental refresh** - MdIncrementalRefreshSettle messages with update actions (new, change, delete)
- **High-precision pricing** - PriceNull9 composite with 10^-9 exponent for price fields
- **Nanosecond timestamps** - Transaction time in nanoseconds since Unix epoch
