## EdgaEquities One Feed: Cboe EDGA Consolidated Market Data Bundle

Consolidated market data bundle for Cboe US Equities EDGA Exchange combining top of book, last sale, and administrative events into a single multicast feed.

### Overview

One Feed is the consolidated market data product for Cboe US Equities EDGA Exchange, bundling top of book quotations, last sale trade reports, trading status, and administrative events into a single Udp multicast stream. It simplifies integration for subscribers that want the full low-depth picture of the venue without having to subscribe to multiple separate feeds.

Messages use the Cboe Pitch binary format and are distributed over Ip multicast with A and B feed redundancy. A Tcp gap request proxy service provides replay for subscribers that miss packets on the multicast feed.

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of sequenced binary market data messages with per-packet sequence numbers and A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Consolidated bundle** - Top, last sale, and administrative events in one feed
- **Simplified integration** - Single subscription replaces multiple feed bundles
- **Cboe Pitch** - Native Cboe binary message format
- **Multicast delivery** - Udp multicast with A and B feed redundancy
- **Gap request proxy** - Tcp recovery service for missed multicast messages

