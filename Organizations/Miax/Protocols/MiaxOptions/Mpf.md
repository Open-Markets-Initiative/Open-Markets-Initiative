## MiaxOptions Mpf: Miax Product Feed

Reference-data feed publishing the list of tradable products, their state, and product-level configuration for the Miax Options Exchange.

### Overview

Miax Product Feed (Mpf) is a reference-data feed for the Miax Options Exchange publishing the list of tradable products, their trading state, and product-level configuration. Subscribers use Mpf alongside the Ais series feed to build a complete picture of available instruments for the current session.

The feed shares the Miax Express binary format and is distributed over Ip multicast with A and B channel redundancy. Subscribers use the Miax Express Session Manager (ESesM) Tcp service for gap fill and last value refresh recovery.

### Transport

Udp multicast for real-time delivery of sequenced Miax Express binary product reference messages, with primary and secondary multicast channels for redundancy. Tcp session via Miax ESesM for gap fill and last value refresh of messages missed on the multicast feed.

### Key Characteristics

- **Product reference** - Tradable product list with state and configuration
- **Miax Express** - Native binary message format for the Miax platform
- **Multicast delivery** - Udp multicast with A and B channel redundancy
- **Last value refresh** - Intra-day recovery without a full day gap fill
- **Gap fill** - Miax ESesM session for recovery of missed multicast messages

