## C1Options Market Level2: Cboe Options Level Two Market Data

Level 2 aggregated depth market data feed publishing price-level book state for options listed on the Cboe Options Exchange.

### Overview

Market Level 2 is an aggregated price-level market data product for the Cboe Options Exchange (C1), publishing top-of-book quotations plus additional price levels beyond the best bid and offer. It is positioned between the simple top of book feed and the full Pitch depth of book, giving subscribers a compact view of the most traded price levels.

### Transport

Udp multicast for real-time delivery of Level 2 price-level depth messages with per-packet sequence numbers for gap detection. Tcp for the Cboe recovery service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Aggregated depth** - Multiple price levels beyond top of book
- **Cboe Options** - Coverage of the C1 Options Exchange
- **Multicast delivery** - Udp multicast distribution of price-level messages
- **Gap recovery** - Tcp recovery service for missed multicast messages
- **Bandwidth efficient** - Compact alternative to full depth of book

