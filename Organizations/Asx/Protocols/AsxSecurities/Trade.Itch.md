## AsxSecurities Trade.Itch: Asx Trade Equities Itch Market Data

Binary market data protocol publishing real-time order and trade events for equities traded on the Asx Trade platform with support for tailor made combinations and iceberg orders.

### Overview

Asx Trade Itch is the binary market data protocol for the Asx Trade cash equities platform. It delivers order-by-order events including new orders, order modifications, trades, and auction equilibrium price updates, enabling subscribers to build a complete order book view and trade ticker for listed Asx equities.

The protocol supports standard limit orders as well as undisclosed orders, iceberg orders, and tailor made combinations, with scenario-driven example messages documenting the event stream for each order type. A companion Glimpse snapshot service provides Tcp access to full book snapshots that can be used to initialise state without replaying the entire trading day.

### Transport

Udp multicast for the live Asx Trade Itch feed, carrying sequenced binary messages for real-time delivery of order book and trade events. Tcp to the Glimpse snapshot service for on-demand full book snapshots and end-of-snapshot indicators, used by subscribers to initialise order book state.

### Key Characteristics

- **Equities market data** - Real-time order and trade events for Asx listed equities
- **Order-by-order** - Full depth of book reconstruction from individual order events
- **Glimpse snapshot** - Tcp snapshot service for book state initialisation
- **Iceberg orders** - Supported as a distinct order type with specific trade scenarios
- **Tailor made combinations** - Multi-leg instruments with dedicated trade handling
- **Auction events** - Equilibrium price update messages during the auction phase
- **Binary encoded** - Compact fixed-width Itch-style messages for low latency processing

