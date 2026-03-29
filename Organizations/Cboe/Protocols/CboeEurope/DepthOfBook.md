## Cboe Europe Depth Of Book

Pitch multicast feed providing full order-level depth of book for Cboe European equity venues.

### Overview

Europe Depth Of Book delivers real-time order-by-order market data for instruments traded on Cboe Europe's regulated market and multilateral trading facilities. The feed shows individual order add, modify, and cancel activity for European equities, exchange-traded funds, and exchange-traded products.

The feed covers instruments across Cboe Europe's trading venues, providing complete book visibility for participants in European equity markets. Messages include order priority information, execution reports, and instrument-level trading status updates.

### Transport

Udp multicast with sequenced delivery and spin server gap recovery.

### Key Characteristics

- **Order-level granularity** - Individual order activity for full book reconstruction
- **European venue coverage** - Data from Cboe Europe regulated market and Mtf venues
- **Multi-instrument** - Equities, Etfs, and exchange-traded products
- **Real-time executions** - Trade messages with price, quantity, and condition codes
