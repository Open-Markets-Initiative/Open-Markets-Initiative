## CxjEquities Multicast Depth Of Book: Cboe Japan Full Depth Of Book Data

Full depth of book Pitch feed publishing order add, modify, reduce, delete, and execute events for equities traded on Cboe Japan (CXJ) on the Cboe Titanium platform.

### Overview

Multicast Depth Of Book is the full depth of book market data feed for Cboe Japan (CXJ), delivered in the Cboe Pitch binary message format. The feed publishes order-by-order events including Add Order, Modify Order, Reduce Size, Delete Order, and Order Executed so that subscribers can reconstruct the complete order book for every instrument.

Messages are distributed over Ip multicast and complemented by a Tcp Gap Request Proxy service for recovery of missed multicast messages and per-unit Spin Servers for order book snapshots. Trade messages report executions against the non-displayed portion of iceberg orders, Trade Break messages report cancelled executions, and Trading Status messages carry the session state and short sell price check flag.

### Transport

Udp multicast via the Cboe Pitch Sequenced Unit Header framing for real-time delivery of sequenced binary market data messages with A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service and the per-unit Spin Server used by subscribers to recover messages missed on the multicast feed or to obtain a snapshot of the open order book.

### Key Characteristics

- **Full depth of book** - Order-by-order add, modify, reduce, delete, and execute events
- **Cboe Pitch** - Native Cboe binary message format on the Cboe Titanium platform
- **Multicast delivery** - Udp multicast with A and B feed redundancy
- **Gap Request Proxy** - Tcp recovery service for missed multicast messages
- **Spin Server** - Per-unit Tcp service for snapshots of the open order book
- **Trading status** - Per-symbol trading state with a short sell price check flag

