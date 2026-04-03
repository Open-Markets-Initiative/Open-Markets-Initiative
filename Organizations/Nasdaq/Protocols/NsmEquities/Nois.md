## NsmEquities Nois: Nasdaq Stock Market Net Order Imbalance Snapshot

Itch market data feed providing periodic snapshots of net order imbalance data for Nasdaq Stock Market cross auctions.

### Overview

Nois delivers snapshot-based net order imbalance data for Nasdaq opening and closing crosses. Unlike NoiView which provides continuous updates, Nois disseminates imbalance information at scheduled intervals, providing a lower-bandwidth alternative for subscribers who do not need tick-by-tick imbalance changes.

The feed uses Itch binary encoding and reports the same core imbalance data as NoiView including paired quantity, imbalance direction and size, reference price, and indicative clearing price. Snapshots are published at defined intervals during the pre-open and pre-close auction periods.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Snapshot-based** - Periodic imbalance data rather than continuous updates
- **Cross auction data** - Paired quantity, imbalance, and indicative prices
- **Lower bandwidth** - Reduced message rate compared to NoiView
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
