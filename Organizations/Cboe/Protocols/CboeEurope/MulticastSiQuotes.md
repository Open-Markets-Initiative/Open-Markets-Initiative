## CboeEurope Multicast Si Quotes: Cboe Europe Systematic Internaliser Quotes

Systematic Internaliser (SI) quote publication feeds carrying SI quotes as Expanded Add Order and Delete Order messages. Part of the Cboe Titanium Europe Multicast PITCH specification and its wire message format.

### Overview

Systematic Internaliser (SI) quote publication feeds carrying SI quotes as Expanded Add Order and Delete Order messages, as section 1.7 of the Cboe Titanium Europe Multicast PITCH specification describes.

### Transport

Udp multicast via the Cboe Pitch Sequenced Unit Header for real-time delivery of sequenced binary market data with A and B feed redundancy. Tcp for the Cboe Europe Gap Request Proxy / spin server used to recover messages missed on the multicast feed.

### Key Characteristics

- **Cboe Pitch** - Native Cboe binary message format, shared with the BXE, CXE and DXE books
- **Multicast delivery** - Udp multicast with gap request proxy recovery

