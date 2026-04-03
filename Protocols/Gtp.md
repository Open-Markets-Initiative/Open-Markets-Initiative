## GTP: Group Ticker Plant

Proprietary binary market data protocol developed by LSEG (London Stock Exchange Group) as part of the Millennium Exchange technology suite, providing a consolidated real-time data feed across multiple LSEG venues and asset classes.

### Overview

The Group Ticker Plant (GTP) is LSEG's standardized real-time market data feed technology, built on a common architecture to deliver low-latency market data across the group's trading venues. GTP serves as the consolidated market data dissemination layer for the Millennium Exchange platform, supporting multiple asset classes including cash equities, fixed income, and derivatives within a single binary protocol framework.

GTP evolved through several phases of development, during which legacy market data protocols including the earlier Level 2 MITCH feed were consolidated into a single bespoke binary protocol optimized for performance. All application messages carry nanosecond-granularity timestamps in UTC, supporting precise time-series analysis and regulatory requirements.

The protocol supports multiple service lines including Level 1 (top of book), Level 2 snapshot, Level 2 incremental (order-by-order), and index data such as FTSE indices. GTP is deployed across the London Stock Exchange, Turquoise, and TRADEcho venues. A recovery service allows clients to request snapshots of the order book for any active instrument to resynchronize after data loss.

### Transport

GTP delivers real-time market data via UDP multicast over IPv4. Data is broadcast across load-balanced multicast channels with instruments distributed across channels as defined in the product guide. The protocol supports dual-feed redundancy with two identically sequenced multicast feeds (Feed A and Feed B) for arbitration. For recovery, GTP provides TCP-based replay services for up to 65,000 recent messages per channel and a snapshot recovery service for full order book resynchronization.

### Key Characteristics

- **Consolidated architecture** - Single binary protocol serving all LSEG venues and asset classes
- **Nanosecond timestamps** - All application messages timestamped with nanosecond granularity in UTC
- **Multi-asset class** - Supports cash equities, fixed income, and derivatives
- **Dual-feed redundancy** - Two identically sequenced multicast feeds for reliability
- **Replay and recovery** - TCP replay for recent gaps (up to 65,000 messages) and snapshot recovery for larger resynchronization
- **MiFID compliance** - Trade messages include regulatory details for post-trade transparency
