## SapphireOptions Liquidity Feed: Miax Sapphire Options Liquidity Feed

Auction and liquidity-event feed publishing price improvement, opening, and crossing auction notifications for the Miax Sapphire Options Exchange.

### Overview

Sapphire Options Liquidity Feed (Slf) publishes auction events for the Miax Sapphire Options Exchange — price improvement auctions, opening rotations, and other crossing events — letting subscribers monitor liquidity opportunities and trade against advertised interest. The feed complements Top Of Market with auction-specific detail not present in the summary quote stream.

The feed shares the Miax Express binary format used across all Miax sub-exchanges. Messages are distributed over Ip multicast with A and B channel redundancy, and subscribers use the Miax Express Session Manager (ESesM) Tcp service for gap fill and recovery.

### Transport

Udp multicast for real-time delivery of sequenced Miax Express binary auction and liquidity event messages, with primary and secondary multicast channels for redundancy. Tcp session via Miax ESesM for gap fill and recovery of messages missed on the multicast feed.

### Key Characteristics

- **Price improvement auctions** - Notifications of price improvement and crossing auctions seeking liquidity
- **Opening rotation** - Opening process event notifications
- **Miax Express** - Native binary message format for the Miax platform
- **Multicast delivery** - Udp multicast with A and B channel redundancy
- **Gap fill** - Miax ESesM session for recovery of missed multicast messages

