## NsmEquities Aggregated: Nasdaq Stock Market Aggregated Feed

Itch market data feed providing aggregated price level data for Nasdaq Stock Market securities.

### Overview

The Aggregated feed delivers consolidated price level data for Nsm-listed and Upa securities, combining order book depth with trade information in a single aggregated stream. The feed provides total displayed quantity at configurable price levels, offering a bandwidth-efficient alternative to full depth of book feeds.

The feed uses Itch binary encoding and includes the standard Nsm system event, stock directory, and trading action reference data messages. Price level updates reflect the net effect of order activity at each price point.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Price level aggregation** - Consolidated size at each price level
- **Combined data** - Order book depth and trade information in one stream
- **Bandwidth efficient** - Lower message rate than order-by-order feeds
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
