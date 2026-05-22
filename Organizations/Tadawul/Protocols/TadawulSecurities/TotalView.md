## TadawulSecurities Total View: Saudi Exchange X-stream Itch Total View Order By Order Market Data

Full depth of book Itch market data feed publishing every order added to the book and every trade executed, plus index values, theoretical opening prices, and orderbook reference price changes for Saudi Exchange listed securities.

### Overview

Total View is the full-depth order-by-order Itch feed for the Saudi Exchange. It publishes every order add, modify, cancel, and execution event, enabling subscribers to reconstruct the complete state of each orderbook in real time.

The feed also disseminates index values and constituent membership, theoretical opening prices and quantities for auctions, and reference, close, settlement, and last-trade prices via the Orderbook Price message. A companion Glimpse snapshot service over SoupBinTcp provides full book snapshots for late-joining subscribers and intraday recovery.

### Transport

Point-to-point delivery via SoupBinTcp for client connections to the Total View feed. One-to-many distribution via MoldUdp64 multicast for the Total View feed (planned future support).

### Key Characteristics

- **Order-by-order** - Full depth of book reconstruction from individual order add, modify, cancel, and execute events
- **Auction support** - Indicative price and quantity messages for opening, intraday, and closing auctions
- **Index publication** - Index member directory and index value messages alongside the underlying orderbook events
- **X-stream platform** - Nasdaq X-stream matching engine licensed and operated by the Saudi Exchange
- **Glimpse snapshot** - Tcp snapshot service for late-joining subscribers and intraday recovery
- **Itch encoded** - Compact fixed-width Itch-style binary messages for low latency processing

