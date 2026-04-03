## Mitch: Lseg Millennium Itch Level 2

Market data protocol for disseminating Level 2 order book and trade data from Lseg venues, predecessor to the Group Ticker Plant.

### Overview

Mitch is Lseg's Millennium Itch protocol, a binary market data feed that provided Level 2 order-by-order data for the London Stock Exchange and Turquoise venues. The protocol delivers individual order add, modify, delete, and execution messages, enabling subscribers to reconstruct the complete order book at full depth for all traded instruments. Mitch was part of Lseg's Millennium Exchange technology platform.

Mitch served as the primary Level 2 market data protocol before the introduction of the Group Ticker Plant (Gtp) as Lseg's unified data platform. The protocol carries reference data, trading status, order book events, trade reports, and auction information through a sequential binary message stream. Mitch shares architectural similarities with other Itch-family protocols used across global exchange venues.

### Transport

Tcp with a session layer providing connection management, sequencing, and recovery. Messages are delivered as a sequential stream with sequence numbers for ordering and gap detection. Recovery services support retransmission of missed messages.

### Key Characteristics

- **Order-by-order data** - Individual order add, modify, delete, and execution messages
- **Full book depth** - Complete order book reconstruction from order-level events
- **Millennium platform** - Part of Lseg's Millennium Exchange technology stack
- **Binary encoded** - Fixed-format binary messages for efficient low-latency parsing
- **Predecessor to Gtp** - Original Level 2 feed before Group Ticker Plant unification
- **Itch family** - Shares architectural lineage with other Itch-variant protocols
