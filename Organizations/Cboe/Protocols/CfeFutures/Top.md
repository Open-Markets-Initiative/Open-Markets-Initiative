## Cboe Cfe Futures Top Of Book

Pitch feed providing best bid and offer updates for contracts on Cboe Futures Exchange.

### Overview

Futures Top Of Book delivers lightweight real-time best bid and offer data for contracts traded on Cboe Futures Exchange. The feed provides top-of-book quotes without the overhead of full depth, suitable for low-latency and bandwidth-sensitive consumers.

The feed includes best bid and offer updates, last sale information, and trading status messages for all listed futures contracts. It provides an efficient alternative to the full depth feed for participants requiring only best price visibility.

### Transport

Udp multicast with sequenced delivery and spin server gap recovery.

### Key Characteristics

- **Best bid and offer** - Real-time top-of-book quotes for futures contracts
- **Low bandwidth** - Compact messages without full depth overhead
- **Last sale data** - Trade execution reports alongside quote updates
- **Trading status** - Contract-level halt, resume, and status notifications
