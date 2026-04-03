## NtxEquities Bbo: Nasdaq Ntx Best Bid And Offer

Itch market data feed providing best bid and offer quotation updates for Nasdaq Ntx securities.

### Overview

Bbo delivers top-of-book price and size updates for all Ntx-listed securities. The feed provides a simplified view reporting only the best bid and best offer rather than the full order book depth.

The feed uses Itch binary encoding and shares the common Ntx reference data message set including stock directory and trading status information. Quote updates reflect changes to the best bid or offer for each security.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Top-of-book** - Best bid and offer price and size only
- **Lower bandwidth** - Reduced message volume compared to depth feeds
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
- **Nanosecond timestamps** - High-resolution event timing
