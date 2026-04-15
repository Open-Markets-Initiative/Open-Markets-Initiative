## EdgaEquities Top: Cboe EDGA Best Bid And Offer Data

Real-time top of book feed publishing best bid and offer quotations and last sale trades for equities traded on Cboe US Equities EDGA Exchange.

### Overview

Top is the top of book market data feed for Cboe US Equities EDGA Exchange, publishing best bid and best offer updates along with last sale trade reports for every listed equity instrument. It is a lightweight alternative to the full depth of book Pitch feed, designed for subscribers that only need current quotations.

Messages are delivered in the Cboe Pitch binary message format, distributed over Ip multicast with A and B feed redundancy for resilience, and a companion Tcp gap request proxy service provides replay of messages missed on the multicast feed.

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of sequenced binary market data messages with per-packet sequence numbers and A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Top of book** - Best bid and best offer for every Cboe US Equities EDGA Exchange instrument
- **Cboe Pitch** - Native Cboe binary message format
- **Multicast delivery** - Udp multicast with A and B feed redundancy
- **Trade reports** - Last sale messages published alongside quotes
- **Gap request proxy** - Tcp recovery service for missed multicast messages
- **Trading status** - System event and instrument-level status notifications

