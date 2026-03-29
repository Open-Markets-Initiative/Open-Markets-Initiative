## NsmEquities Bbo: Nasdaq Stock Market Best Bid And Offer

Itch market data feed providing best bid and offer quotation updates for Nasdaq Stock Market securities.

### Overview

Bbo delivers top-of-book price and size updates for all Nsm-listed and Upa securities. The feed provides a simplified view compared to TotalView, reporting only the best bid and best offer rather than the full order book depth, making it suitable for subscribers who need current quote information without order-level detail.

The feed uses Itch binary encoding and shares the common Nsm reference data message set including stock directory, trading action, and system event messages. Quote updates reflect changes to the national best bid or offer for each security.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Top-of-book** - Best bid and offer price and size only
- **Lower bandwidth** - Reduced message volume compared to depth feeds
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
- **Nanosecond timestamps** - High-resolution event timing
