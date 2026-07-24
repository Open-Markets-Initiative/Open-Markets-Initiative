## Securities Index Refresh: Orion Market Data Cash Index Refresh

UDP multicast refresh service companion to OMD-C Index — publishes periodic snapshots of index reference and value state per §4.4. Carries Index Definition and Index Data snapshots; terminated by Refresh Complete.

### Overview

Refresh channel is UDP multicast, structurally identical to the real-time channel but publishes state snapshots rather than event streams. Retransmission service does not cover the refresh channel — if the client misses a snapshot, it must wait for the next one.

### Transport

Udp multicast on the refresh channel corresponding to the real-time index channel (per §2698).

