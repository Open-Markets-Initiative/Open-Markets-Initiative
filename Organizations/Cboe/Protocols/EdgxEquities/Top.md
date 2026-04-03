## Cboe Edgx Equities Top Of Book

Pitch feed providing best bid and offer updates for Cboe Edgx Equities Exchange.

### Overview

Equities Top Of Book delivers lightweight real-time best bid and offer data for instruments traded on Cboe Edgx Equities Exchange. The feed provides Nbbo-contributing quote updates without the overhead of full depth of book, making it suitable for low-latency and bandwidth-sensitive consumers.

The feed includes top-of-book quote changes, last sale information, and trading status messages. It serves as an efficient alternative to the full depth feed for participants who only require best price visibility.

### Transport

Udp multicast with sequenced delivery and spin server gap recovery.

### Key Characteristics

- **Best bid and offer** - Real-time top-of-book quote updates
- **Low bandwidth** - Compact messages without full depth overhead
- **Last sale included** - Trade execution data alongside quote updates
- **Trading status** - Halt, resume, and instrument status notifications
