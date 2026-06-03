## EmeraldOptions Order Feed: Miax Emerald Options Order Feed (Mor)

Real-time order feed publishing simple and complex displayed orders on the Miax Emerald Exchange along with series, strategy, system state, and trading status messages.

### Overview

Emerald Options Order Feed (Mor) is the order-level market data feed for the Miax Emerald Exchange, publishing displayed simple and complex orders along with the reference data needed to interpret them. The feed carries Open and Close lifecycle events for resting displayed orders so subscribers can maintain a current view of the displayed order book.

The protocol shares its transport and session model with the other Emerald feeds, using Udp multicast for live distribution and the Miax Express Session Manager (ESesM) over Tcp for gap fill. Auction and immediate orders such as Prime, Ioc, Fok, Iso, and complex crossing orders are not disseminated; the feed is restricted to resting displayed orders eligible for liquidity interaction.

### Transport

Udp multicast for real-time delivery of sequenced Miax Express binary order messages, with primary and secondary multicast channels for redundancy. Tcp session via Miax ESesM for gap fill and last value refresh of messages missed on the multicast feed.

### Key Characteristics

- **Simple and complex orders** - Resting displayed orders for simple options and multi-leg complex strategies
- **Order lifecycle** - Open and Close messages for displayed orders
- **Miax Express** - Native binary message format for the Miax platform
- **Multicast delivery** - Udp multicast with A and B channel redundancy
- **Gap fill** - Miax ESesM session for recovery of missed multicast messages
- **Reference data carry** - Series, complex strategy, system state, and trading status messages embedded in the feed
- **Displayed only** - Quotes, eQuotes, auction, and immediate orders are not disseminated

