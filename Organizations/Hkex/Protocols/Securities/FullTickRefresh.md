## Securities Full Tick Refresh: Orion Market Data Cash FullTick Refresh

UDP multicast refresh service companion to OMD-C FullTick (SF) — publishes periodic snapshots of market state per §4.4. Carries the SF-applicable subset of refresh-service messages: reference data, status, VCM trigger, Add Order snapshots for all non-empty books, order imbalance, IEP, reference price; terminated by Refresh Complete. Only state-carrying messages are snapshotted; transient Modify Order, Delete Order, Trade, and Trade Cancel events are not.

### Overview

Refresh channel is UDP multicast, structurally identical to the real-time channel but publishes state snapshots rather than event streams. Add Order messages on the refresh channel represent the current live order book (all non-empty books) rather than event notifications. Retransmission service does not cover the refresh channel — if the client misses a snapshot, it must wait for the next one.

### Transport

Udp multicast on the refresh channel corresponding to each real-time channel (per §2698).

