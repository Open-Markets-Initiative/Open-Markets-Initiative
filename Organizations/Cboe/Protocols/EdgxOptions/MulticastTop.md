## EdgxOptions Multicast Top: Cboe EDGX Options Multicast Best Bid And Offer Data

Udp multicast top of book feed publishing best bid and offer quotations for options traded on Cboe EDGX Options Exchange.

### Overview

Multicast Top is the Udp multicast variant of the Cboe EDGX Options Top feed, delivering best bid and offer quotation updates for options over Ip multicast with A and B feed redundancy. It is the preferred transport for latency-sensitive subscribers that want direct multicast delivery rather than Tcp unicast.

The message format is consistent with other Cboe Pitch feeds, using compact binary records for low-latency decoding. A Tcp gap request proxy service is available for subscribers that miss packets on the multicast feed or need to resynchronize.

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of sequenced binary market data messages with per-packet sequence numbers and A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Top of book** - Best bid and best offer for every Cboe EDGX Options Exchange instrument
- **Multicast only** - Udp multicast distribution without a Tcp direct channel
- **Cboe Pitch** - Native Cboe binary message format
- **A and B redundancy** - Dual multicast channels for resilience
- **Gap request proxy** - Tcp recovery service for missed multicast messages

