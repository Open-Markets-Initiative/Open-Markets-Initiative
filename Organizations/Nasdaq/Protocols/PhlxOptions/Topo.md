## PhlxOptions Topo: Nasdaq Phlx Top Of Options Market

Itch market data feed providing best bid and offer for options traded on the Nasdaq Phlx exchange.

### Overview

Topo delivers top-of-book quotation updates for all options series listed on Phlx. The feed reports the best bid and best offer price and size for each series, providing a lightweight view of the Phlx options market.

The feed uses Itch binary encoding and includes Phlx-specific options reference data messages for series directory, trading action, and system events. Quote updates reflect changes to the best displayed bid or offer for each options series.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Top-of-book** - Best bid and offer price and size for each series
- **Lower bandwidth** - Reduced message volume compared to depth feeds
- **Options-specific** - Series directory with underlying, expiration, strike, and type
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
