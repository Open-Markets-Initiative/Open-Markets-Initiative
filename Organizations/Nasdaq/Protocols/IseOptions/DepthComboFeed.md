## IseOptions DepthComboFeed: Nasdaq Ise Options Depth Combo Feed

Itch market data feed providing aggregated depth for complex options strategies on the Nasdaq Ise exchange.

### Overview

DepthComboFeed delivers aggregated price level depth information for complex multi-leg options strategies traded on Ise. Unlike OrderComboFeed which provides individual order detail, DepthComboFeed aggregates interest at each net price level for each strategy.

The feed uses Itch binary encoding and provides price level updates as complex orders are added, modified, or removed. Each strategy is defined by its component legs with series and ratio references.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Aggregated complex depth** - Net price level data for multi-leg strategies
- **Lower bandwidth** - Aggregated rather than order-by-order complex data
- **Strategy definitions** - Leg components with series and ratio references
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
