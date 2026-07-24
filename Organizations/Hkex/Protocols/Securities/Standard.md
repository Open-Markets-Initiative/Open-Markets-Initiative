## Securities Standard: Orion Market Data Cash Standard

Hkex Orion Market Data Cash Standard (SS) is the aggregated depth-of-book securities market data product for the Hkex securities market. SS delivers aggregate order book updates, the priority Broker Queue with top-40 broker IDs per side, order imbalance at IEP, per-security trade tickers combining consecutive same-price trades, closing prices, nominal prices, indicative equilibrium prices, reference prices for POS and CAS, VCM triggers, per-security statistics with turnover and VWAP, market turnover per segment, bond yields, and exchange news. SS omits order-level Add/Modify/Delete events (available in FullTick) and individual trade messages (available in Premium and FullTick).

### Overview

SS is the entry-level cash-market product in the Orion Market Data Cash (OMD-C) family, sized for use cases that need aggregated depth, priority broker information, and per-security trade and price context without full order-level granularity. The aggregated book, broker queue, and trade ticker messages minimise message rate compared to FullTick while still supporting most professional market data display and analytics workflows.

SS shares the OMD packet header, framing, control, and refresh messages with the other cash-market products (Premium, FullTick, Index). Consumers of SS can switch to Premium or FullTick with no changes to the framing layer.

### Transport

Udp multicast delivery on dual A and B channels with per-channel sequence numbers.

### Key Characteristics

- **Aggregate order book** - Depth of book updates per price level, not per order
- **Broker Queue** - Top 40 broker IDs per side with spread level markers
- **Trade ticker** - Consecutive same-price trades aggregated into single messages
- **Per-security statistics** - Turnover, shares traded, high/low/last, short-sell activity
- **News integrated** - Exchange news messages carried on the market data feed

