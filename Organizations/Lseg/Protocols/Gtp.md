## Gtp: Lseg Group Ticker Plant Consolidated Market Data

Consolidated ticker plant market data protocol publishing real-time quotation and trade events across London Stock Exchange Group markets.

### Overview

Gtp is the London Stock Exchange Group ticker plant feed, a consolidated market data product that aggregates real-time quotes and trades across Lseg venues into a single downstream stream. It provides a normalised view of the Lseg market for data vendors, redistributors, and subscribers who need cross-venue coverage in one feed.

Messages are distributed over Ip multicast as sequenced binary records with compact fixed-width fields for low-latency processing. Tcp retransmission and snapshot services provide the recovery path for subscribers who miss packets on the multicast feed or need to initialise state mid-day.

### Transport

Udp multicast for real-time delivery of consolidated ticker plant messages with per-packet sequence numbers for gap detection. Tcp for the ticker plant retransmission and snapshot services used by subscribers to recover missed multicast messages.

### Key Characteristics

- **Consolidated feed** - Aggregated market data across Lseg venues
- **Ticker plant architecture** - Normalised quotes and trades delivered to downstream subscribers
- **Multicast delivery** - Real-time Udp multicast distribution with sequence numbers
- **Retransmission and snapshots** - Tcp recovery services for gap fill and mid-day startup
- **Binary encoded** - Fixed-width compact binary messages for efficient processing
- **Cross-venue** - Covers multiple Lseg trading platforms in one feed

