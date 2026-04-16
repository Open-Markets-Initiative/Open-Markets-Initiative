## C1Options Market Data Feed: Cboe Options Market Data Feed

Legacy Cboe options market data feed publishing quote, trade, and administrative events for Cboe listed options.

### Overview

Market Data Feed (Mdf) is the legacy Cboe options market data product, publishing quote updates, trade reports, and administrative events for options listed on the Cboe Options Exchange. It predates the Pitch family of feeds but remains available for subscribers that have integrated against the legacy Mdf message format.

### Transport

Udp multicast for real-time delivery of Cboe Market Data Feed binary messages with per-packet sequence numbers for gap detection. Tcp for the market data feed recovery service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Legacy format** - Pre-Pitch Cboe options market data feed
- **Multicast delivery** - Udp multicast distribution of quote and trade messages
- **Trade reports** - Last sale messages with conditions
- **Gap recovery** - Tcp recovery service for missed multicast messages
- **Cboe Options** - Coverage of the Cboe Options Exchange (C1)

