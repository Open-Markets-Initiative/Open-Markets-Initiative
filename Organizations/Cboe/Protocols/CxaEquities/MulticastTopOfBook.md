## CxaEquities Multicast Top Of Book: Cboe Australia Top Of Book Data

Top of book Pitch feed publishing best bid and ask updates and trade events for equities traded on Cboe Australia (CXA) on the Cboe Titanium platform. Approximately 66% smaller than the full depth of book feed by event count and byte volume.

### Overview

Multicast Top Of Book is the top of book market data feed for Cboe Australia (CXA), delivered in the Cboe Pitch binary message format. The feed publishes Single Side Update and Two Side Update messages providing aggregated best bid and best ask price and size. TOP Trade messages carry executions inline. This is a lower-bandwidth alternative to the full depth of book feed for clients that only need inside prices.

Messages are distributed over Ip multicast with A and B feed redundancy and complemented by a Tcp Gap Request Proxy service for recovery of missed multicast messages and per-unit Spin Servers for intraday top of book snapshots. Trade reports, calculated values, and auction events (Auction Update, Auction Summary) are carried inline with the price updates for a complete top of book view.

### Transport

Udp multicast via the Cboe Pitch Sequenced Unit Header framing for real-time delivery of sequenced binary market data messages with A and B feed redundancy across primary and secondary datacentres. Tcp for the Cboe Grp Gap Request Proxy service and the per-unit Spin Server used by subscribers to recover messages missed on the multicast feed or to obtain an intraday snapshot of the top of book state.

### Key Characteristics

- **Top of book** - Aggregated best bid and best ask price and size updates via Single Side Update and Two Side Update messages
- **Cboe Pitch** - Native Cboe binary message format on the Cboe Titanium platform
- **Multicast delivery** - Udp multicast with A and B feed redundancy across primary and secondary datacentres
- **Bandwidth efficient** - Approximately 66% smaller than the full depth of book Pitch feed by event count and byte volume
- **Trade reports** - On-exchange executions and off-exchange trade reports published alongside price updates via TOP Trade messages
- **Auction events** - Opening, closing, intraday, and halt-reopening auction update and summary messages
- **Gap Request Proxy** - Tcp recovery service for missed multicast messages
- **Spin Server** - Per-unit Tcp service for intraday top of book snapshots (Order Count is always zero for TOP spins)
- **Trading status** - Per-symbol trading state notifications including pre-open, pre-close, halted, and suspended states
- **Calculated values** - Index, iNAV, closing price, and end-of-day NAV values disseminated inline

