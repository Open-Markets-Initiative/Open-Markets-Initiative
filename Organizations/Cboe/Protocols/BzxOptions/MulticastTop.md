## Cboe Bzx Options Multicast Top Of Book

Pitch multicast feed providing best bid and offer updates for individual options series on Cboe Bzx Options Exchange.

### Overview

Options Multicast Top Of Book delivers lightweight real-time best bid and offer data for options series traded on Cboe Bzx Options Exchange. The feed provides Bbo quote updates without the overhead of full order-level depth, making it efficient for consumers requiring only top-of-book visibility.

The feed covers all listed options series on the exchange. It includes top-of-book quote changes, last sale information, and trading status messages for each options series.

### Transport

Udp multicast with sequenced delivery and spin server gap recovery.

### Key Characteristics

- **Best bid and offer** - Real-time top-of-book quotes for options series
- **Low bandwidth** - Compact messages without full depth overhead
- **Last sale data** - Trade execution reports alongside quote updates
- **Trading status** - Series-level halt, resume, and status notifications
