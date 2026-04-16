## C1Options Opening Auction: Cboe Options Opening Auction Event Data

Dedicated opening auction feed publishing indicative prices, imbalance data, and auction status for options listed on the Cboe Options Exchange.

### Overview

Opening Auction is a dedicated market data feed for the Cboe Options Exchange (C1) that publishes opening auction events including indicative prices, imbalance quantities, auction status, and final auction prints. It allows subscribers to participate in and monitor the opening auction on Cboe Options with the timeliness needed to react to auction state changes.

### Transport

Udp multicast for real-time delivery of opening auction messages with A and B feed redundancy and per-packet sequence numbers. Tcp for the Cboe Grp Gap Request Proxy service used to recover missed multicast messages.

### Key Characteristics

- **Opening auction events** - Indicative prices and imbalance information
- **Dedicated feed** - Focused channel for opening auction data only
- **Cboe Pitch** - Native Cboe binary message format
- **Multicast delivery** - Udp multicast with A and B feed redundancy
- **Gap request proxy** - Tcp recovery service for missed multicast messages

