## PsxEquities Last Sale: Nasdaq PSX Trade Report Feed

Trade report feed publishing executed trade messages for equities traded on Nasdaq PSX Equities.

### Overview

Last Sale is the trade report market data feed for Nasdaq PSX Equities, publishing executed trade messages with price, size, and condition codes as trades occur. It provides a clean last-sale stream for subscribers that need trade information without the overhead of a full depth of book feed.

Messages are delivered in the Cboe Pitch binary format over Ip multicast with A and B feed redundancy, and a Tcp gap request proxy service is available for recovery of messages missed on the multicast feed. Trade cancellations and corrections are published alongside trade reports.

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of sequenced binary market data messages with per-packet sequence numbers and A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Last sale** - Executed trade stream for Nasdaq PSX Equities
- **Trade lifecycle** - Trade report, cancellation, and correction messages
- **Cboe Pitch** - Native Cboe binary message format
- **Multicast delivery** - Udp multicast with A and B feed redundancy
- **Gap request proxy** - Tcp recovery service for missed multicast messages

