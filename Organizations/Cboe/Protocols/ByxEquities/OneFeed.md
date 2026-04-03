## Cboe Byx Equities OneFeed

Pitch feed providing consolidated best bid and offer across all Cboe Us equity exchanges.

### Overview

Equities OneFeed delivers a unified best bid and offer view by aggregating top-of-book quotes from all Cboe Us equity venues into a single consolidated stream. This eliminates the need for subscribers to independently consume and merge data from each individual exchange feed.

OneFeed simplifies market data infrastructure for participants who require cross-venue best price visibility without managing multiple separate feed connections. The feed reflects the best available prices across Bzx, Byx, Edgx, and Edga exchanges.

### Transport

Udp multicast with sequenced delivery and spin server gap recovery.

### Key Characteristics

- **Consolidated Bbo** - Unified best bid and offer across all Cboe equity venues
- **Single feed** - Eliminates multi-feed aggregation complexity
- **Real-time updates** - Reflects cross-venue best price changes as they occur
- **Simplified connectivity** - Reduces infrastructure requirements for Cboe equity data
