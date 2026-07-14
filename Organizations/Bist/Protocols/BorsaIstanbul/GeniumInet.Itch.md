## BorsaIstanbul Genium Inet.Itch: Bist Genium Inet Itch Market Data

Binary market data protocol publishing real-time order book and trade events for securities traded on Borsa Istanbul's BISTECH platform, built on Nasdaq's Genium INET ITCH technology.

### Overview

Bist Genium Inet Itch is the binary market data protocol for Borsa Istanbul's BISTECH platform, which was jointly developed with Nasdaq and derived from Nasdaq's Genium INET trading technology. It delivers order-by-order events including order book directory updates, order additions, modifications, executions, and trades across BIST's equity, debt securities, derivatives (VIOP), and precious metals markets, enabling subscribers to build a complete order book view and trade ticker.

The protocol carries reference data (order book directory, tick size table entries, short sell status), event and state change messages, market by order messages, and trade messages, all delivered over MoldUDP64 multicast with nanosecond-resolution timestamps. A companion Glimpse snapshot service provides TCP access to full book snapshots that can be used to initialise state without replaying the entire trading day.

### Transport

MoldUDP64 multicast for the live Bist Genium Inet Itch feed, carrying sequenced binary messages for real-time delivery of order book and trade events. SoupBinTCP session to the Glimpse snapshot service for on-demand full order book snapshots, used by subscribers to initialise order book state.

### Key Characteristics

- **Multi-market data** - Single consolidated feed spanning equity, debt securities, derivatives (VIOP), and precious metals order books
- **Order-by-order** - Full depth of book reconstruction from individual order events
- **Glimpse snapshot** - Tcp snapshot service for order book state initialisation
- **Genium Inet lineage** - Message formats and transport align with Nasdaq's Genium INET Itch conventions, since BISTECH was jointly developed with Nasdaq
- **Combination instruments** - Supports standard combination order books with grouped executions across constituent legs
- **Binary encoded** - Compact fixed-width Itch-style messages for low latency processing

