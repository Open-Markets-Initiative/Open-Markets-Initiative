## Securities Premium: Orion Market Data Cash Premium

Hkex Orion Market Data Cash Premium (SP) delivers aggregated depth-of-book plus per-trade granularity. SP carries every executed Trade and Trade Cancel event alongside the Aggregate Order Book Update, Order Imbalance, Closing Price, Nominal Price, Indicative Equilibrium Price, Reference Price, VCM Trigger, per-security Statistics, Market Turnover, Yield, and News messages. SP omits order-level Add/Modify/Delete events (available in FullTick), Trade Ticker aggregation (available in SS), and the Broker Queue (available in SS or via the complementary Conflated Broker Queue feed).

### Overview

SP is the mid-tier cash-market product in the Orion Market Data Cash (OMD-C) family, positioned between the aggregated SS (Standard) and the fully order-level SF (FullTick). SP delivers aggregated depth plus every individual trade event and trade cancel, making it suitable for trade-driven analytics such as volume profiling, trade-based signals, VWAP and TWAP calculations, and market-tone monitoring without the message rate of a full order-book feed.

SP shares the OMD packet header, framing, control, and refresh messages with SS, SF, and the Index product. Every trade event carries a microsecond-precision timestamp and a public trade type code identifying automatched, off-exchange, odd-lot, and auction trades.

### Transport

Udp multicast delivery on dual A and B channels with per-channel sequence numbers.

### Key Characteristics

- **Per-trade granularity** - Every executed trade and trade cancel event delivered individually
- **Aggregate order book** - Depth of book updates per price level
- **Microsecond trade timestamps** - Trade time provided to microsecond precision
- **Public trade type coded** - Automatch, off-exchange, odd-lot, auction, overseas trade types identified
- **VWAP included** - Volume-weighted average price populated in Statistics messages

