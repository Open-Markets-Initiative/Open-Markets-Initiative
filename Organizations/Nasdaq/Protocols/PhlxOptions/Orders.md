## PhlxOptions Orders: Nasdaq PHLX Order Book Itch Market Data

Order-by-order Itch market data feed publishing every displayed order on the Nasdaq PHLX Options order book, including add, replace, and cancel events plus per-message timestamps.

### Overview

Orders is the order-by-order Itch market data feed for Nasdaq PHLX Options, publishing every displayed order on the book — add order, order replace, order cancel, and order execution events — using the Nasdaq Itch binary protocol. Subscribers can reconstruct the full order book from this feed and observe every market participant action.

The feed is delivered over MoldUdp64 multicast with a SoupBinTcp Glimpse snapshot and retransmission service for recovery. Every message carries both seconds (via a periodic Timestamp Seconds Message) and per-message nanoseconds for sub-microsecond timestamping.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style binary order events with per-packet sequence numbers and Timestamp Seconds Message anchors. Tcp via SoupBinTcp to the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Order by order** - Every displayed order on the PHLX Options book
- **Nasdaq Itch** - Industry-standard Itch binary format
- **MoldUdp64 multicast** - Nasdaq multicast framing with per-packet sequence numbers
- **Glimpse snapshot** - SoupBinTcp mid-day initialisation and retransmission
- **Per-message timestamps** - Composite seconds + nanoseconds wall-clock timestamps

