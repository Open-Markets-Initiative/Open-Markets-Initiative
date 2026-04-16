## MiaxOptions Top Of Market: Miax Options Best Bid And Offer Feed

Real-time top of market feed publishing best bid and offer quotations and trade reports for simple options contracts listed on the Miax Options Exchange.

### Overview

Miax Options Top Of Market (Tom) is the primary market data feed for the Miax Options Exchange, publishing the best bid and best offer for every simple options series traded on the venue along with last sale trade reports. The feed is delivered in the Miax Express binary format with compact fixed-width messages tuned for options data rates.

Messages are distributed over Ip multicast with A and B channel redundancy for resilience, and subscribers can use the Miax Express Session Manager (ESesM) Tcp service to request gap fill and session recovery. The feed carries not just quotes and trades but also system events, trading status, and auction messages that let subscribers maintain a complete view of Miax Options market state.

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

