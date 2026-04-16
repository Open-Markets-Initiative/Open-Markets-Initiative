## Order Data Feed: SmallX Ats Order And Trade Data Feed

Binary market data feed publishing order and trade events for securities traded on the SmallX alternative trading system.

### Overview

SmallX Order Data Feed is the market data product for the SmallX alternative trading system, publishing real-time order and trade events for securities traded on the venue. The feed is designed for subscribers that need visibility into SmallX order flow and execution activity as it happens.

Messages are delivered as sequenced binary records over Ip multicast with fixed-width fields for low-latency processing. Subscribers receive order add, modify, delete, and execute events along with trade reports and system events so they can reconstruct the SmallX order book and trade stream.

### Transport

Udp multicast for real-time delivery of sequenced binary order and trade messages with per-packet sequence numbers for gap detection.

### Key Characteristics

- **Order and trade feed** - Real-time order events and executed trade reports
- **Ats market data** - Tailored for SmallX alternative trading system subscribers
- **Multicast delivery** - Real-time Udp multicast distribution of the feed
- **Binary encoded** - Fixed-width compact binary message format
- **Sequence numbered** - Per-packet sequence numbers for gap detection

