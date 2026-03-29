## Cboe Byx Equities Auction Feed

Pitch feed providing auction indicative and result data for Cboe Byx Equities Exchange.

### Overview

Equities Auction Feed delivers real-time opening, closing, and intraday auction information for instruments on Cboe Byx Equities Exchange. The feed includes indicative prices, paired and imbalance quantities, and auction result messages throughout the auction process.

Subscribers use this feed to monitor auction progression and participate in price discovery during opening and closing periods. The feed provides continuous updates as order interest changes during the auction collection window.

### Transport

Udp multicast with sequenced delivery and spin server gap recovery.

### Key Characteristics

- **Opening and closing auctions** - Indicative data for scheduled auction events
- **Imbalance information** - Paired quantities and directional imbalance data
- **Auction results** - Final auction prices and executed quantities
- **Continuous updates** - Refreshed indicative data as auction interest changes
