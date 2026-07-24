## ChinaConnect SSERefresh: Orion Market Data China Connect SSE Refresh

UDP multicast refresh service for the OMD-CC Shanghai Stock Exchange (SSE A-Share) real-time channel. Publishes periodic snapshots of market state; terminated by Refresh Complete (203). Provides recovery for large-scale data loss or late start-up.

### Overview

Refresh channel is UDP multicast, structurally identical to the SSE real-time channel but publishes state snapshots rather than event streams.

### Transport

Udp multicast on the refresh channel corresponding to the SSE real-time channel.

