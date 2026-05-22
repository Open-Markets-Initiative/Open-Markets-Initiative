## CoinbaseDeribit Market Data Api: Coinbase Deribit Sbe Multicast Market Data

Sbe-encoded multicast Udp market data api for Coinbase Deribit publishing orders, trades, market state changes, and instrument definitions for crypto options and futures.

### Overview

The Coinbase Deribit market data api is a multicast Udp feed that allows market participants to receive market information for Deribit cryptocurrency options and futures including orders, trades, market state changes, and instrument definitions. The api is organized as multiple groups of data channels and streams for distinct sets of related products and instruments, with each group comprised of several channel pairs.

Messages are encoded using Simple Binary Encoding (Sbe) with fixed-width fields for low-latency decoding. The feed covers the full range of events needed to track Deribit markets and supports both primary and secondary feed pairs for redundancy, allowing subscribers to detect and recover from packet loss on either side.

### Transport

Udp multicast carrying market data channels delivering sequenced Sbe messages for orders, trades, market state, and instrument definitions across the Deribit options and futures product set.

### Key Characteristics

- **Crypto derivatives market data** - Orders, trades, and instrument events for Deribit options and futures
- **Sbe encoded** - Simple Binary Encoding for fixed-width low-latency parsing
- **Multicast delivery** - Udp multicast across multiple channel groups
- **Channel pairs** - A and B feed redundancy for packet loss recovery
- **Product grouping** - Channel groups organized by related option and future product sets
- **Instrument definitions** - Full security reference data including strike, expiry, and option type carried in the feed
- **Market state** - Session and instrument-level trading status transitions

