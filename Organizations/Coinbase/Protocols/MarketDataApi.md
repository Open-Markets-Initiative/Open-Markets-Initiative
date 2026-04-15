## Market Data Api: Coinbase Derivatives Sbe Multicast Market Data

Sbe-encoded multicast Udp market data api for Coinbase Derivatives publishing orders, trades, market state changes, and instrument definitions.

### Overview

The Coinbase Derivatives market data api is a multicast Udp feed that allows market participants to receive market information including orders, trades, market state changes, and instrument definitions. The api is organized as multiple groups of data channels and streams for distinct sets of related products and instruments, with each group comprised of several channel pairs.

Messages are encoded using Simple Binary Encoding (Sbe) with fixed-width fields for low-latency decoding. The feed covers the full range of events needed to track Coinbase Derivatives markets and supports both primary and secondary feed pairs for redundancy, allowing subscribers to detect and recover from packet loss on either side.

### Transport

Udp multicast carrying the market data channel pairs, with each channel delivering sequenced Sbe messages for orders, trades, market state, and instrument definitions.

### Key Characteristics

- **Derivatives market data** - Orders, trades, and instrument events for Coinbase Derivatives
- **Sbe encoded** - Simple Binary Encoding for fixed-width low-latency parsing
- **Multicast delivery** - Udp multicast across multiple channel groups
- **Channel pairs** - A and B feed redundancy for packet loss recovery
- **Product grouping** - Channel groups organized by related product sets
- **Instrument definitions** - Full security reference data in the feed
- **Market state** - Session and instrument-level trading status transitions

