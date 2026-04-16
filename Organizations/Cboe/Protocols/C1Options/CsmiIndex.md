## C1Options Csmi Index: Cboe Streaming Index Value Data

Index value feed publishing real-time Cboe proprietary index level updates for subscribers to Cboe options and volatility products.

### Overview

Csmi Index is the Cboe Streaming Market Index feed, publishing real-time calculated index values for Cboe proprietary indices such as the Cboe Volatility Index (Vix) and other Cboe-branded indices. The feed is used by subscribers who trade index options, futures, and other derivatives priced against Cboe-calculated index values.

### Transport

Udp multicast for real-time delivery of Cboe streaming index value messages with per-packet sequence numbers for gap detection. Tcp for the Cboe Grp Gap Request Proxy service used to recover messages missed on the multicast feed.

### Key Characteristics

- **Cboe proprietary indices** - Vix and other Cboe index values
- **Real-time index levels** - Continuous calculated index updates
- **Cboe Pitch** - Native Cboe binary message format
- **Multicast delivery** - Udp multicast distribution of index values
- **Gap request proxy** - Tcp recovery service for missed multicast messages

