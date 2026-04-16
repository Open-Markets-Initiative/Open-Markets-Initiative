## Genium Inet.Itch: Osaka Securities Exchange Itch Market Data

Itch-based market data feed publishing real-time order book, trade, and reference data for derivatives traded on the Osaka Securities Exchange Jpx Genium Inet platform.

### Overview

Genium Inet Itch is the market data protocol for the Japan Exchange Group Osaka Securities Exchange (Ose), delivering real-time order-by-order events for derivatives including futures and options. The feed publishes order add, modify, delete, trade, and auction messages using the Nasdaq Itch binary protocol adapted for the Genium Inet trading platform.

Messages are distributed over Ip multicast with per-packet sequence numbers for gap detection. A companion Tcp Glimpse snapshot and retransmission service provides book snapshots for mid-day initialisation and replay of messages missed on the multicast feed.

### Transport

Udp multicast for real-time delivery of sequenced Itch-style binary market data messages with per-packet sequence numbers for gap detection. Tcp for the Glimpse snapshot and retransmission services for recovery of missed multicast messages and mid-day initialisation.

### Key Characteristics

- **Order-by-order** - Full depth of book reconstruction from individual order events
- **Osaka derivatives** - Futures and options on Jpx Ose
- **Genium Inet platform** - Nasdaq Genium Inet matching engine
- **Itch encoded** - Nasdaq Itch binary message format
- **Multicast delivery** - Udp multicast with sequence numbers
- **Glimpse recovery** - Tcp snapshot and retransmission services

