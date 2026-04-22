## Pillar: NYSE Pillar Market Data

Proprietary binary market data encoding of the unified NYSE Pillar platform, publishing order-by-order depth of book, trades, imbalances, and security status across all NYSE Group equities and options exchanges.

### Overview

NYSE Pillar is the unified trading technology platform used across NYSE, NYSE Arca, NYSE American, NYSE National, and NYSE Chicago. On the market data side, Pillar publishes a family of proprietary binary feeds that replace the legacy XDP (Exchange Data Publisher) feeds. The flagship Pillar Integrated Feed provides a comprehensive order-by-order view of market events including full depth of book, trades, order imbalances, and security status messages.

Pillar market data messages are encoded in a fixed-length binary format optimized for low-latency parsing. Each message carries a sequence number enabling gap detection, and feeds are delivered on two parallel multicast lines (A and B) per channel so that subscribers can arbitrate between them to mask packet loss. Refresh and retransmission services are available over TCP for gap recovery and intraday snapshots.

The Pillar market data architecture is tightly correlated with Pillar order entry: gateway OrderIDs and DealIDs map directly to OrderIDs and DealIDs in the market data feeds, so order-entry activity can be reconciled against the integrated feed without additional identifier translation.

### Transport

Pillar market data is distributed over UDP multicast with a dual-feed architecture where each channel provides two redundant multicast groups (Line A and Line B) for subscriber arbitration. Data is partitioned across multiple multicast channels for capacity management. Dedicated TCP-based request servers provide refresh and retransmission services for gap recovery and market state snapshots.

### Key Characteristics

- **Unified market data** - Single encoding across all NYSE Group equities and options markets
- **Binary encoding** - Fixed-length binary message format optimized for low-latency parsing
- **Dual-feed redundancy** - Delivered on two parallel multicast lines per channel for reliability
- **Order-by-order depth** - Integrated Feed enables full depth-of-book reconstruction
- **Correlated identifiers** - OrderIDs and DealIDs match the Pillar Stream order-entry gateway
- **Partitioned channels** - Data split across multicast channels for throughput and load balancing
- **Refresh services** - TCP-based refresh and retransmission for gap recovery and snapshots

