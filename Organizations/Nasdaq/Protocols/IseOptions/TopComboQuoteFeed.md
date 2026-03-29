## IseOptions TopComboQuoteFeed: Nasdaq Ise Options Top Combo Quote Feed

Itch market data feed providing best bid and offer for complex options strategies on the Nasdaq Ise exchange.

### Overview

TopComboQuoteFeed delivers top-of-book quotation updates for complex multi-leg options strategies traded on Ise. The feed reports the best bid and offer net price and size for each defined strategy, providing a lightweight view of complex order book interest.

The feed uses Itch binary encoding and includes strategy definition messages that describe the component legs. Quote updates reflect changes to the best displayed complex bid or offer for each strategy.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Top-of-book complex quotes** - Best bid and offer for each strategy
- **Lower bandwidth** - Minimal message volume for complex market data
- **Strategy definitions** - Leg components with series and ratio references
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
