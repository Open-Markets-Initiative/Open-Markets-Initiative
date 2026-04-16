## Esp: Currenex Forex Executable Streaming Prices

Itch-based market data protocol delivering executable streaming forex prices from Market Makers to Market Participants over low latency Tcp and Udp transports.

### Overview

Esp is the Currenex Executable Streaming Prices service, publishing foreign exchange executable prices from Market Makers to Market Participants who can then place orders against the prices received. The wire format uses a Currenex-specific subset of the Itch protocol optimized for forex streaming prices with compact fixed-width binary messages.

The service is delivered over reliable high-speed physical networks such as Lan cross connects or metro area direct circuits and is not supported on the public internet or low-performance connections. Itch is supported on both Tcp for guaranteed delivery and Udp for low-latency datagram delivery on low-loss networks, with minimal differences between the two transports at the message level.

### Transport

Tcp for reliable delivery of Itch streaming price messages over low-latency physical networks such as Lan cross connects or metro area direct circuits. Udp for low-latency datagram delivery of Itch streaming price messages on low-loss networks, with per-packet sequence numbers for gap detection.

### Key Characteristics

- **Forex executable streaming prices** - Real-time two-way prices for currency pairs
- **Itch encoded** - Compact fixed-width binary message format
- **Dual transport** - Tcp for reliability, Udp for low latency on controlled networks
- **Market maker to participant** - Prices flow from liquidity providers to price takers
- **Controlled delivery** - Dedicated physical networks, not public internet
- **Low latency** - Designed for high-speed forex trading workloads

