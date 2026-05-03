## TadawulSecurities Itch: Saudi Exchange X-stream Itch Order By Order Market Data

X-stream Itch market data feed publishing real-time order and trade events for equities, sukuk, exchange traded funds, and real estate investment trusts traded on the Saudi Exchange Nasdaq X-stream matching engine.

### Overview

Tadawul Securities Itch is the binary market data protocol distributed by the Saudi Exchange over its Nasdaq X-stream platform. It delivers order-by-order events including new orders, order modifications, deletions, and executions, enabling subscribers to build a complete limit order book and trade ticker for every listed Tadawul security.

The protocol carries reference data, trading status changes, order book events, and trade messages within a single sequenced multicast stream, with a companion Glimpse snapshot service that provides full book snapshots over Tcp for late-joining subscribers and intraday recovery.

### Transport

Udp multicast for the live X-stream Itch feed, carrying sequenced binary messages for real-time delivery of order book and trade events. Tcp to the Glimpse snapshot service for on-demand full book snapshots and end-of-snapshot indicators, used by subscribers to initialise order book state.

### Key Characteristics

- **Equities market data** - Real-time order and trade events for Saudi Exchange listed securities
- **Order-by-order** - Full depth of book reconstruction from individual order events
- **X-stream platform** - Nasdaq X-stream matching engine licensed and operated by the Saudi Exchange
- **Glimpse snapshot** - Tcp snapshot service for book state initialisation and intraday recovery
- **Reference data** - Security definitions and trading status integrated with the feed
- **Itch encoded** - Compact fixed-width Itch-style binary messages for low latency processing

