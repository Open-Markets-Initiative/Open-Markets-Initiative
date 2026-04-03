## Gtp: Lseg Group Ticker Plant

Market data protocol for disseminating real-time order book and trade data from the London Stock Exchange, Turquoise, and TradeEcho venues.

### Overview

Gtp is Lseg's Group Ticker Plant, the current-generation market data dissemination platform serving the London Stock Exchange, Turquoise multilateral trading facility, and TradeEcho trade reporting service. The protocol delivers a comprehensive binary data feed including order-by-order book updates, trade reports, auction information, reference data, and trading status for all instruments across these venues.

Gtp replaced the earlier Mitch protocol as Lseg's primary market data feed, providing a unified data platform across multiple venues under the Lseg group. The protocol carries Level 2 order book data with individual order add, modify, delete, and execution messages, enabling subscribers to reconstruct the full depth of book. Gtp supports equities, exchange-traded funds, fixed income, and other instrument types traded on Lseg venues.

### Transport

Tcp with a session layer providing connection management, sequencing, and recovery. Messages are delivered as a sequential stream with sequence numbers for ordering. Recovery services allow subscribers to request retransmission of missed messages.

### Key Characteristics

- **Multi-venue coverage** - London Stock Exchange, Turquoise, and TradeEcho in a single feed
- **Order-by-order data** - Individual order add, modify, delete, and execution messages
- **Full book depth** - Complete order book reconstruction from order-level events
- **Binary encoded** - Fixed-format binary messages for efficient low-latency parsing
- **Auction support** - Opening, closing, and intraday auction indicative prices and results
- **Unified platform** - Successor to Mitch providing consolidated Lseg venue data
