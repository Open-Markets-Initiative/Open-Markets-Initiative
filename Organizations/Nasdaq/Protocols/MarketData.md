## Market Data: Nasdaq Nordic Genium INET AMD

Binary auxiliary market data feed of the Nasdaq Nordic Genium INET platform, carrying the order book and market directories, the tick size table, reported and broken trades, quote requests, open interest, prices, market depth by level and underlying prices.

### Overview

The feed opens each trading day by disseminating an Order book Directory for every active instrument, including halted ones, followed by the Market Directory, the legs of each combination order book and the tick size table. Intra-day directory messages follow when instruments are added or changed, so a reader builds its reference data from the stream rather than from a file.

Thirteen message types carry the whole feed. Two are the feed talking about itself - the Seconds message that carries Unix time and the System Event message that opens and closes the day - four are reference data, and the remaining seven are the market: reported trades and their cancellations, quote requests, open interest, prices, aggregated depth by level and the price of the underlying.

### Transport

MoldUDP64 multicast, which sequences the stream so a receiver can tell that it has missed something and ask for it again. SoupBinTcp for recovery and for a session wanting a reliable ordered stream rather than multicast.

### Key Characteristics

- **Reference data on the stream** - Directories are disseminated at the open and intra-day, not fetched
- **Depth by level** - Market by Level carries the aggregate at each of the best price levels
- **Fixed extent messages** - Every message is a flat record of fixed width, with no repeating group anywhere
- **Derivatives and commodities** - The markets the Genium INET platform runs, rather than the Inet equity markets

