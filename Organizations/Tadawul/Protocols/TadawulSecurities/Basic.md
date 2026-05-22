## TadawulSecurities Basic: Saudi Exchange X-stream Itch Top Of Book Market Data

Top of book Itch market data feed publishing best bid offer changes, every trade executed, and all index values for Saudi Exchange listed securities, without order-by-order detail.

### Overview

Basic is the top-of-book Itch feed for the Saudi Exchange. It publishes Best Bid Offer changes for each orderbook rather than every order event, giving subscribers a lighter-weight view of market state when full depth is not required.

The feed also carries trade messages, index values and constituents, and reference, close, and settlement prices via the Orderbook Price message.

### Transport

Point-to-point delivery via SoupBinTcp for client connections to the Basic feed.

### Key Characteristics

- **Top of book** - Best Bid Offer messages disseminating the inside market for each orderbook
- **Trade publication** - Every trade executed in the market is published with execution price, quantity, and trade indicator
- **Index publication** - Index member directory and index value messages alongside the orderbook events
- **X-stream platform** - Nasdaq X-stream matching engine licensed and operated by the Saudi Exchange
- **Lower bandwidth** - No order-by-order events results in lower throughput than the Total View feed
- **Itch encoded** - Compact fixed-width Itch-style binary messages for low latency processing

