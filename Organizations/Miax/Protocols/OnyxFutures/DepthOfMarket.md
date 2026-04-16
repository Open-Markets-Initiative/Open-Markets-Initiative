## OnyxFutures Depth Of Market: Miax Onyx Futures Full Depth Of Book Feed

Real-time full depth of book feed publishing aggregated price-level quotes and trade reports for futures contracts traded on the Miax Onyx Futures Exchange.

### Overview

Onyx Futures Depth Of Market is the aggregated depth of book market data feed for the Miax Onyx Futures Exchange, publishing price-level quote updates, aggregated quantities, and last sale trade reports for every futures contract traded on the venue. The feed is designed for subscribers that need more granularity than top of book while avoiding the volume of a full order-by-order feed.

Messages are distributed over Ip multicast with A and B channel redundancy, using the Miax Express binary format. Subscribers use the Miax Express Session Manager (ESesM) Tcp service for gap fill and session recovery. The feed carries quotes, trades, system events, and trading status messages for a complete view of the Onyx futures market.

### Transport

Udp multicast for real-time delivery of sequenced Miax Express binary depth of book messages, with primary and secondary multicast channels for redundancy. Tcp session via Miax ESesM for gap fill and recovery of messages missed on the multicast feed.

### Key Characteristics

- **Depth of book** - Aggregated price-level book state
- **Miax Express** - Native binary message format for the Miax platform
- **Multicast delivery** - Udp multicast with A and B channel redundancy
- **Trade reports** - Last sale messages published alongside depth updates
- **Gap fill** - Miax ESesM session for recovery of missed multicast messages
- **Trading status** - System event and instrument-level status notifications
- **Futures focused** - Designed for Onyx futures trading hours and conventions

