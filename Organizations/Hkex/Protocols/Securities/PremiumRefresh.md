## Securities Premium Refresh: Orion Market Data Cash Premium Refresh

UDP multicast refresh service companion to OMD-C Premium (SP) — publishes periodic snapshots of market state per §4.4. Carries the SP-applicable subset of refresh-service messages (reference data, status, VCM trigger, aggregate order book, order imbalance, closing/nominal/IEP/reference prices, statistics, market turnover, yield, news); terminated by Refresh Complete. No Broker Queue snapshots (available only in SS).

### Overview

Refresh channel is UDP multicast, structurally identical to the real-time channel but publishes state snapshots rather than event streams. Retransmission service does not cover the refresh channel — if the client misses a snapshot, it must wait for the next one.

### Transport

Udp multicast on the refresh channel corresponding to each real-time channel (per §2698).

