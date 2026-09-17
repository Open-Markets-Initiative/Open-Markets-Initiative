## Tsx Quantum Feed: Toronto Stock Exchange And TSX Venture Exchange Quantum Feed Level 1 And Level 2

Market data feed publishing real-time order book, quote, and trade data for equities traded on the Toronto Stock Exchange and TSX Venture Exchange.

### Overview

Quantum Feed is the Toronto Stock Exchange market data product, publishing real-time quote and trade events for equities listed on the Toronto Stock Exchange and TSX Venture Exchange in a single feed. The feed is available in Level 1 and Level 2 tiers, where Level 1 carries top of book quotations and Level 2 carries aggregated depth of book for subscribers that need visibility beyond the best bid and offer.

### Transport

Udp multicast via the Sola transport framing for real-time delivery of sequenced messages with per-packet sequence numbers for gap detection. Tcp for the Sola gap fill and retransmission services used by subscribers to recover missed multicast messages.

### Key Characteristics

- **TSX and TSXV** - Coverage of Toronto Stock Exchange and TSX Venture Exchange listings
- **Level 1 and Level 2** - Top of book and aggregated depth tiers
- **Multicast delivery** - Udp multicast distribution of the feed
- **Gap recovery** - Tcp gap fill and retransmission service
- **Binary encoded** - Compact fixed-width binary messages

