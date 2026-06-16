## MiaxOptions Order Feed: Miax Options Resting Order Feed

Order-by-order resting market depth feed publishing add, modify, and delete events for every visible order on the Miax Options Exchange book.

### Overview

Miax Options Order Feed (Mor) publishes every add, modify, and delete on the Miax Options resting order book, letting subscribers reconstruct the full depth-of-book and follow individual order lifecycles. The feed complements the Top Of Market and Complex Top Of Market summary feeds with full order-by-order detail.

Messages share the Miax Express binary format and are distributed over Ip multicast with A and B channel redundancy. Subscribers use the Miax Express Session Manager (ESesM) Tcp service to request gap fill and session recovery when multicast packets are lost.

### Transport

Udp multicast for real-time delivery of sequenced Miax Express binary order events, with primary and secondary multicast channels for redundancy. Tcp session via Miax ESesM for gap fill and recovery of messages missed on the multicast feed.

### Key Characteristics

- **Order by order book** - Add, modify, and delete events for every visible order
- **Miax Express** - Native binary message format for the Miax platform
- **Multicast delivery** - Udp multicast with A and B channel redundancy
- **Gap fill** - Miax ESesM session for recovery of missed multicast messages

