## SmallFutures Order Data Feed: SmallX Order And Trade Data Feed

Binary market data feed publishing order and trade events for the futures and options on futures listed by the Small Exchange.

### Overview

The Order Data Feed is the Small Exchange market data product, publishing real-time order and trade events for the contracts it lists. The feed is designed for subscribers that need visibility into order flow and execution activity as it happens.

Messages are delivered as sequenced binary records over Ip multicast with fixed-width fields for low-latency processing. Subscribers receive order add, modify, delete, and execute events along with trade reports and system events so they can reconstruct the order book and trade stream.

### Transport

Udp multicast for real-time delivery of sequenced binary order and trade messages with per-packet sequence numbers for gap detection.

### Key Characteristics

- **Order and trade feed** - Real-time order events and executed trade reports
- **Futures market data** - Futures and options on futures listed by the Small Exchange
- **Multicast delivery** - Real-time Udp multicast distribution of the feed
- **Binary encoded** - Fixed-width compact binary message format
- **Sequence numbered** - Per-packet sequence numbers for gap detection

