## Securities Full Tick: Orion Market Data Cash FullTick

Hkex Orion Market Data Cash FullTick (SF) is the full order-level securities market data product for the Hkex cash market. SF publishes every order-book event as it happens (Add Order, Modify Order, Delete Order) plus every executed Trade and Trade Cancel with microsecond precision, alongside Order Imbalance at IEP, Indicative Equilibrium Price, Reference Price, and VCM Trigger messages. SF omits the aggregated order book (available in SS and SP), Trade Ticker aggregation, Nominal Price, Closing Price, Statistics, Market Turnover, Yield, and News (all available in SS or SP).

### Overview

SF is the premium cash-market product in the Orion Market Data Cash (OMD-C) family, delivering the highest granularity of order-book activity for co-located and low-latency trading systems. Consumers rebuild the full limit order book from the stream of Add, Modify, and Delete Order events plus the corresponding Trade and Trade Cancel messages. All prices use 3 implied decimal places; trade times are provided to microsecond precision.

SF shares the OMD packet header, framing, control, and refresh messages with SS, SP, and the Index product. Because SF carries order-level events rather than aggregated snapshots, the peak message rate is significantly higher than SS or SP.

### Transport

Udp multicast delivery on dual A and B channels with per-channel sequence numbers.

### Key Characteristics

- **Order-level events** - Add, Modify, and Delete Order messages for every order-book change
- **Full order book reconstruction** - Complete limit order book rebuildable from the stream
- **Per-trade granularity** - Every executed trade and trade cancel event delivered individually
- **Microsecond timestamps** - Trade time provided to microsecond precision
- **Low-latency focus** - Highest-granularity feed sized for co-located consumers

