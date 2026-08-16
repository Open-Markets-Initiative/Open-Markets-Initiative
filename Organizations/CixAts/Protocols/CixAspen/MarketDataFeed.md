## CixAspen Market Data Feed: CIX Market Data Feed

Binary market data feed publishing resting orders, cancels, executions, symbol reference data, and market/symbol state for the CIX ATS.

### Overview

The CIX Market Data Feed is CIX's Aspen-encoded depth feed, publishing all resting orders, cancels, and executions across the CIX ASPEN, CIX ASPEN VERT, and CIX MIDPOINT venues. It also provides symbol reference data, overall market state, and individual symbol trading state (halts).

Messages are delivered as a sequenced binary stream over Ip multicast with fixed-width fields for low-latency processing. Each venue and channel (A/B redundant pair) is disseminated on its own multicast group, all sharing a single Udp port per site.

### Transport

Udp multicast for real-time delivery of sequenced binary order and execution messages with per-packet sequence numbers for gap detection.

### Key Characteristics

- **Full order book** - Resting orders, cancels, and executions for the CIX ATS
- **Binary encoded** - Fixed-width compact binary messages for low latency
- **Multicast delivery** - Real-time Udp multicast distribution with redundant A/B feeds
- **Sequence numbered** - Per-packet sequence numbers for gap detection
- **Reference data** - Symbol definitions and trading state published on the feed

