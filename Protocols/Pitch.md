## Pitch: Cboe Multicast Depth of Book

Proprietary binary market data protocol originally developed by BATS Global Markets and now maintained by Cboe Global Markets, providing real-time order-by-order and trade data across equities, options, futures, and international markets.

### Overview

Pitch is the primary market data dissemination protocol for Cboe Global Markets. It delivers full depth-of-book information on a per-order basis, enabling subscribers to reconstruct the complete state of the order book at any point in time. Each message reflects the addition, deletion, modification, or execution of an order in the matching engine, providing the highest granularity of market data available from Cboe venues.

The protocol was originally created by BATS Global Markets for its US equity exchanges (BZX, BYX, EDGA, and EDGX) and was carried forward when Cboe acquired BATS in 2017. It has since been extended to cover Cboe options exchanges, the Cboe Futures Exchange (CFE), and Cboe international venues in Europe, Australia, Japan, and Canada. Pitch is available in multiple feed configurations including Depth of Book, Top of Book, Last Sale, and Auction feeds.

Pitch uses a fixed-length binary message format with little-endian byte ordering. All messages within a feed are sequenced, allowing subscribers to detect gaps and recover missed data. The protocol is delivered under the Cboe Titanium infrastructure, with separate multicast groups assigned per matching unit or product group. A TCP variant of Pitch is also available for US equities, providing reliable delivery for firms that do not require the lowest possible latency.

### Transport

Pitch primarily operates over UDP multicast for real-time market data distribution. Each matching unit publishes data on dedicated multicast groups, with separate channels for incremental updates and recovery snapshots. Packets consist of a sequenced packet header followed by one or more Pitch messages. A TCP-based Pitch feed is also available for certain US equity markets.

### Key Characteristics

- **Full depth of book** - Every visible order add, modify, cancel, and execution event is published individually
- **Little-endian binary encoding** - Fixed-length messages with unsigned binary fields in little-endian byte order
- **Sequenced messages** - Each packet carries a sequence number for gap detection and recovery
- **Multiple feed levels** - Depth of Book, Top of Book, Last Sale, and Auction feed variants available
- **Multi-asset class** - Supports equities, options (including complex instruments), futures, and futures options
- **Symbol mapping** - Mapping messages link short feed symbols to full instrument identifiers
- **Retail price improvement** - Retail Liquidity Indicator messages signal when retail price-improving orders are available
- **Auction support** - Auction Update messages disseminate indicative price and imbalance information
