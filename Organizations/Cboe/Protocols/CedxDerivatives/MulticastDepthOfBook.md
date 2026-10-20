## CedxDerivatives Multicast Depth Of Book: Cboe Europe Derivatives Full Depth Of Book Data

Full depth of book Cboe Pitch multicast feed publishing order add, modify, cancel and execute events for instruments traded on Cboe Europe Derivatives (MIC CEDX). Defined by the Cboe Europe CEDX Multicast PITCH specification.

### Overview

Multicast Depth Of Book is the full depth of book market data feed for Cboe Europe Derivatives, delivered in the Cboe Pitch binary message format over Ip multicast with A and B feed redundancy. It publishes order-by-order add, modify, delete and execute events plus trade, auction and trading-status messages so subscribers can reconstruct the complete order book.

The CEDX Multicast PITCH is its own specification, separate from the Cboe Titanium Europe Multicast PITCH that the BXE, CXE and DXE equities books share.

### Transport

Udp multicast via the Cboe Pitch Sequenced Unit Header for real-time delivery of sequenced binary market data with A and B feed redundancy. Tcp for the Cboe Europe Gap Request Proxy / spin server used to recover messages missed on the multicast feed.

### Key Characteristics

- **Full depth of book** - Order-by-order add, modify, cancel and execute events
- **Cboe Pitch** - Native Cboe binary message format
- **Multicast delivery** - Udp multicast with A and B feed redundancy
- **Gap recovery** - Tcp gap request proxy / spin server for missed messages

