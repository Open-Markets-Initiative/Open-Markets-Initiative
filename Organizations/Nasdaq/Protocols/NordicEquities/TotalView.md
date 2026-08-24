## NordicEquities Total View: Nasdaq Nordic Full Depth Of Book Feed

Full depth of book market data feed for the Nasdaq Nordic equities markets running on the Inet Nordic platform.

### Overview

Nordic Equity TotalView is the order by order depth of book feed for the Nasdaq Nordic cash equity markets. Every displayed order is published as it is added, executed, cancelled, replaced or deleted, so subscribers can maintain a complete view of the book rather than an aggregated summary.

Alongside the order flow the feed carries order book directory reference data, trading state changes, cross trades, broken trades and the imbalance indicators published during the opening, closing, intraday and auction on demand crosses. Prices are integers with an implied precision and timestamps are nanoseconds since midnight Utc.

### Transport

Udp multicast framed by Mold Udp 64 carrying a session identifier, a sequence number for the first message in the packet and a count of the message blocks that follow.

### Key Characteristics

- **Order by order depth** - Every displayed order published individually rather than aggregated
- **Reference data** - Order book directory with symbol, Isin, currency and note codes
- **Auction imbalance** - Noii and auction on demand Moii imbalance indicators
- **Mold Udp 64** - Udp multicast framing with sequenced message blocks

