## Securities Standard Refresh: Orion Market Data Cash Standard Refresh

UDP multicast refresh service companion to OMD-C Standard (SS) — publishes periodic snapshots of market state per §4.4 so that clients can recover from large-scale data loss or synchronise after a late start. Carries snapshots of reference data (market/security/liquidity provider/currency rate), status (trading session, security status, VCM trigger), aggregate order book, broker queue, order imbalance, closing/nominal/indicative-equilibrium/reference prices, per-security statistics, market turnover, yield, news; terminated by Refresh Complete.

### Overview

Refresh channel is UDP multicast, structurally identical to the real-time channel but publishes state snapshots rather than event streams. Retransmission service does not cover the refresh channel — if the client misses a snapshot, it must wait for the next one.

### Transport

Udp multicast on the refresh channel corresponding to each real-time channel (per §2698).

