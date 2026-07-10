## Overnight Top Of Book: Aggregated top-of-book channel for OTC Link Overnight OTC

Aggregated top-of-book channel publishing best bid and offer events for OTC extended-hours markets. Carries a subset of the wire vocabulary — Top of Book snapshots, Security / Security Flag reference, Trading Session lifecycle, plus Start of Spin / End of Spin brackets. Used by OTC Link Overnight OTC, the overnight quotation platform for OTC equities; consumers subscribed only for best bid/offer do not need to process the full order-by-order Depth of Book channel.

### Overview

OTC Top of Book is the aggregated best-bid-and-offer channel published in parallel to the Depth of Book channel for OTC extended-hours markets. Consumers who only need top-of-book pricing subscribe here to avoid processing the full order-by-order stream. The wire format shares the same packet and message framing as the DepthOfBook channel; the difference is content — only aggregated top-of-book snapshots plus lifecycle and reference messages are published.

Recovery is via A/B feed arbitration for real-time redundancy. Gap fills and mid-session snapshots are obtained through the companion Retransmission TCP service which serves both DepthOfBook and Top channels.

### Transport

UDP multicast for real-time delivery of sequenced binary top-of-book snapshots. Each packet carries a 12-byte packet header (sequence number, packet flag, message count, packet time-of-day) followed by concatenated messages framed by a 3-byte message header (MessageSize + MessageType). Redundant A/B multicast feeds for arbitration.

### Key Characteristics

- **Aggregated top-of-book** - Best bid and offer prices without individual order visibility
- **Overnight coverage** - OTC Link Overnight OTC session (18:00 to 07:45 Eastern)
- **Bandwidth-efficient subscription** - Alternative to Depth of Book for consumers who only need top-of-book pricing
- **A/B multicast redundancy** - Redundant A and B feeds for arbitration and gap detection
- **Shared retransmission service** - Recovery via the Retransmission TCP channel that also serves Depth of Book

