## MiaxOptions Complex Top Of Market: Miax Options Complex Order Book Top Of Market

Real-time top of market feed publishing best bid and offer quotations and trade reports for complex multi-leg options strategies on the Miax Options Exchange.

### Overview

Miax Options Complex Top Of Market (Ctom) is the market data feed for the complex order book on the Miax Options Exchange. It publishes the best bid and best offer for multi-leg strategies such as spreads, straddles, and combinations along with trade reports for executed complex orders, delivered in the Miax Express binary format.

The protocol shares its transport and session model with the simple Miax Options Top Of Market feed, using Udp multicast for live distribution and the Miax Express Session Manager (ESesM) over Tcp for gap fill. Complex strategy definitions, trading status changes, and auction messages for the complex book are all carried within the same sequenced feed.

### Transport

Udp multicast for real-time delivery of sequenced Miax Express binary complex strategy quote and trade messages, with primary and secondary multicast channels for redundancy. Tcp session via Miax ESesM for gap fill and recovery of messages missed on the multicast feed.

### Key Characteristics

- **Complex book** - Top of book for multi-leg options strategies
- **Strategy definitions** - Complex instrument definitions published on the feed
- **Miax Express** - Native binary message format for the Miax platform
- **Multicast delivery** - Udp multicast with A and B channel redundancy
- **Trade reports** - Last sale messages for executed complex trades
- **Gap fill** - Miax ESesM session for recovery of missed multicast messages
- **Complex auctions** - Auction messages for the complex order book

