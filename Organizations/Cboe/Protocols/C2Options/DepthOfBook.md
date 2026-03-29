## Cboe C2 Options Depth Of Book

Pitch multicast feed providing full order-level depth of book for Cboe C2 Options Exchange.

### Overview

Options Depth Of Book delivers real-time order-by-order market data for options series traded on Cboe C2 Options Exchange. The feed shows individual order add, modify, and cancel activity, enabling subscribers to reconstruct the complete limit order book for each options series.

Messages include order priority information, execution reports, and series-level trading status updates.

### Transport

Udp multicast with sequenced delivery and spin server gap recovery.

### Key Characteristics

- **Order-level granularity** - Individual order activity for full book reconstruction
- **Series-level data** - Per-series order book and trading status information
- **Real-time executions** - Trade messages with price, quantity, and condition codes
