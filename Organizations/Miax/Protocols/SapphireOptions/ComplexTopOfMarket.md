## SapphireOptions Complex Top Of Market: Miax Sapphire Options Complex Best Bid And Offer Feed

Real-time top of market feed publishing best bid and offer quotations and trade reports for complex multi-leg option strategies listed on the Miax Sapphire Options Exchange.

### Overview

Sapphire Options Complex Top Of Market (cTom) publishes the best bid and best offer for every complex multi-leg option strategy traded on the Miax Sapphire Options Exchange along with last sale trade reports. Strategies include spreads, straddles, butterflies, and other defined combinations. The feed complements the simple-series Top Of Market with multi-leg coverage.

Messages share the Miax Express binary format and are distributed over Ip multicast with A and B channel redundancy. Subscribers use the Miax Express Session Manager (ESesM) Tcp service to request gap fill and session recovery.

### Transport

Udp multicast for real-time delivery of sequenced Miax Express binary complex quote and trade messages, with primary and secondary multicast channels for redundancy. Tcp session via Miax ESesM for gap fill and recovery of messages missed on the multicast feed.

### Key Characteristics

- **Complex strategy top of book** - Best bid and offer for complex multi-leg strategies
- **Miax Express** - Native binary message format for the Miax platform
- **Multicast delivery** - Udp multicast with A and B channel redundancy
- **Trade reports** - Last sale messages published alongside quotes
- **Gap fill** - Miax ESesM session for recovery of missed multicast messages

