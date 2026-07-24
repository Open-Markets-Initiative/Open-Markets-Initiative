## Securities Combined Refresh: Orion Market Data Cash Combined Refresh

UDP multicast refresh service superset — includes every refresh-eligible OMD-C message across all products and complementary feeds (Odd Lot, Stock Connect) per §4.4. Intended for captures that mix refresh channels or for development/QA where a single refresh dissector is preferred over per-product dissectors.

### Overview

Refresh channel is UDP multicast, structurally identical to the real-time channel but publishes state snapshots rather than event streams. Retransmission service does not cover the refresh channel — if the client misses a snapshot, it must wait for the next one.

### Transport

Udp multicast on any refresh channel per §4.4.

