## Cboe Options Auction Feed

Pitch feed providing auction indicative and result data for options series on Cboe Options Exchange.

### Overview

Options Auction Feed delivers real-time opening auction and improvement mechanism data for options series traded on Cboe Options Exchange. The feed includes indicative prices, paired quantities, and auction results during opening and intraday auction processes.

The feed supports participants monitoring the auction process for options series, providing continuous updates as order interest changes.

### Transport

Udp multicast with sequenced delivery and spin server gap recovery.

### Key Characteristics

- **Opening auctions** - Indicative data for scheduled options opening auctions
- **Improvement mechanisms** - Data from price improvement auction processes
- **Auction results** - Final executed prices and quantities
