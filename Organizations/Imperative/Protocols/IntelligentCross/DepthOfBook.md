## IntelligentCross Depth Of Book: Imperative Intelligent Cross Equities Market Data

Binary market data feed publishing match events and reference data for the Imperative Intelligent Cross Ats periodic auction venue.

### Overview

The Intelligent Cross Market Data Feed is the venue's Aspen-encoded depth feed, publishing match events and related reference data for the Intelligent Cross alternative trading system. Intelligent Cross is a frequent periodic auction venue for Nms equities, and the feed exposes the auction match events downstream to subscribers that want real-time visibility into venue activity.

Messages are delivered as a sequenced binary stream over Ip multicast with fixed-width fields for low-latency processing. Subscribers receive auction match messages, security reference data, and operational events so they can track the state of the Intelligent Cross venue throughout the trading day.

### Transport

Udp multicast for real-time delivery of sequenced binary match and reference data messages with per-packet sequence numbers for gap detection.

### Key Characteristics

- **Periodic auction** - Match events from the Intelligent Cross Ats
- **Binary encoded** - Fixed-width compact binary messages for low latency
- **Multicast delivery** - Real-time Udp multicast distribution of the feed
- **Sequence numbered** - Per-packet sequence numbers for gap detection
- **Reference data** - Security definitions published on the feed
- **Ats market data** - Designed for subscribers to the Intelligent Cross venue

