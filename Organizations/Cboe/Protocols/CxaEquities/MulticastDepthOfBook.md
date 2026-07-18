## CxaEquities Multicast Depth Of Book: Cboe Australia Full Depth Of Book Data

Full depth of book Pitch feed publishing order add, modify, cancel, and execute events for equities traded on Cboe Australia (CXA) on the Cboe Titanium platform.

### Overview

Multicast Depth Of Book is the full depth of book market data feed for Cboe Australia (CXA), delivered in the Cboe Pitch binary message format. The feed publishes order-by-order events including Add Order, Modify Order, Reduce Size, Delete Order, Order Executed, and Order Executed at Price so that subscribers can reconstruct the complete order book for every listed instrument.

Messages are distributed over Ip multicast with A and B feed redundancy and complemented by a Tcp Gap Request Proxy service for recovery of missed multicast messages and per-unit Spin Servers for intraday order book snapshots. Trade reports, trade breaks, calculated values, and auction events (Auction Update, Auction Summary) are carried inline with the order events for a complete view of the market.

### Transport

Udp multicast via the Cboe Pitch Sequenced Unit Header framing for real-time delivery of sequenced binary market data messages with A and B feed redundancy across primary and secondary datacentres. Tcp for the Cboe Grp Gap Request Proxy service and the per-unit Spin Server used by subscribers to recover messages missed on the multicast feed or to obtain an intraday snapshot of the open order book.

### Key Characteristics

- **Full depth of book** - Order-by-order add, modify, reduce, cancel, and execute events
- **Cboe Pitch** - Native Cboe binary message format on the Cboe Titanium platform
- **Multicast delivery** - Udp multicast with A and B feed redundancy across primary and secondary datacentres
- **Trade reports** - On-exchange executions and off-exchange trade reports published alongside order events
- **Auction events** - Opening, closing, intraday, and halt-reopening auction update and summary messages
- **Gap Request Proxy** - Tcp recovery service for missed multicast messages
- **Spin Server** - Per-unit Tcp service for intraday snapshots of the open order book
- **Trading status** - Per-symbol trading state notifications including pre-open, pre-close, halted, and suspended states
- **Calculated values** - Index, iNAV, closing price, and end-of-day NAV values disseminated inline

