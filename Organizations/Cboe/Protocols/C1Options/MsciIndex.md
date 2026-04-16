## C1Options Msci Index: Cboe Msci Index Value Data

Index value feed publishing real-time Msci index level updates for subscribers to Cboe Msci index options and futures products.

### Overview

Msci Index is the Cboe feed publishing real-time calculated Msci index values for subscribers who trade options and futures priced against Msci-branded indices. Cboe distributes the Msci index levels directly on a dedicated channel so that derivatives market participants can track the underlying index value alongside their options and futures positions.

### Transport

Udp multicast for real-time delivery of Msci index value messages with per-packet sequence numbers for gap detection. Tcp for the Cboe recovery service used to recover messages missed on the multicast feed.

### Key Characteristics

- **Msci indices** - Real-time Msci index level values
- **Derivatives underlying** - Used for Msci options and futures pricing
- **Multicast delivery** - Udp multicast distribution of index values
- **Gap recovery** - Tcp recovery service for missed multicast messages
- **Dedicated channel** - Separate feed channel for Msci index data

