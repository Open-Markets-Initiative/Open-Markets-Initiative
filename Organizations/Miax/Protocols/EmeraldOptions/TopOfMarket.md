## EmeraldOptions Top Of Market: Miax Emerald Options Best Bid And Offer Feed

Real-time top of market feed publishing best bid and offer quotations and trade reports for simple options contracts listed on the Miax Emerald Exchange.

### Overview

Emerald Options Top Of Market (Tom) is the top of book market data feed for the Miax Emerald Exchange, publishing the best bid and best offer for every simple options series traded on the venue along with last sale trade reports. The feed uses the Miax Express binary format shared across all Miax sub-exchanges.

Messages are distributed over Ip multicast with A and B channel redundancy, and subscribers use the Miax Express Session Manager (ESesM) Tcp service for gap fill and recovery. The feed carries quotes, trades, system events, trading status, and auction messages so that subscribers can maintain a complete view of Miax Emerald market state.

### Transport

Udp multicast for real-time delivery of sequenced Miax Express binary quote and trade messages, with primary and secondary multicast channels for redundancy. Tcp session via Miax ESesM for gap fill and recovery of messages missed on the multicast feed.

### Key Characteristics

- **Options top of book** - Best bid and offer for simple options series
- **Miax Express** - Native binary message format for the Miax platform
- **Multicast delivery** - Udp multicast with A and B channel redundancy
- **Trade reports** - Last sale messages published alongside quotes
- **Auction events** - Opening, closing, and price improvement auction messages
- **Gap fill** - Miax ESesM session for recovery of missed multicast messages
- **Trading status** - System event and instrument-level status notifications

