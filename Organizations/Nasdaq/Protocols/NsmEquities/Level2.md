## NsmEquities Level2: Nasdaq Stock Market Level 2

Itch market data feed providing aggregated price level depth for Nasdaq Stock Market securities.

### Overview

Level2 delivers aggregated order book depth information showing the total displayed size at each price level for Nsm-listed and Upa securities. Unlike TotalView which provides individual order detail, Level2 aggregates all orders at each price level into a single size, offering a more compact representation of market depth.

The feed uses Itch binary encoding and provides price level updates as orders are added, modified, or removed from the book. It includes the standard Nsm reference data messages for stock directory and trading status information.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Aggregated depth** - Total size at each price level rather than individual orders
- **Lower bandwidth** - More compact than order-by-order TotalView
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
- **Multiple price levels** - Visible depth beyond top of book
