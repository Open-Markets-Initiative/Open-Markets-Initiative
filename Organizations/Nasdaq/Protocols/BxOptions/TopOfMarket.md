## BxOptions TopOfMarket: Nasdaq Bx Options Top Of Market

Itch market data feed providing best bid and offer for options traded on the Nasdaq Bx Options exchange.

### Overview

TopOfMarket delivers top-of-book quotation updates for all options series listed on Bx Options. The feed reports the best bid and best offer price and size for each series, providing a bandwidth-efficient alternative to the full DepthOfMarket feed.

The feed uses Itch binary encoding and includes the standard Bx Options reference data messages. Quote updates reflect changes to the best displayed bid or offer for each options series.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Top-of-book** - Best bid and offer price and size for each series
- **Lower bandwidth** - Reduced message volume compared to depth feeds
- **Options-specific** - Series directory with underlying, expiration, strike, and type
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
