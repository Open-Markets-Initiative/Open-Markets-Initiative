## CurrenexForex Now: Currenex Forex Spot Market Data

Itch-based market data service providing real-time access to Currenex Forex spot market data through multiple distinct feed channels.

### Overview

Currenex Now is the Currenex forex spot market data service, providing real-time access to executable prices and trade events for spot currency pairs. The service is comprised of several distinct market data feeds each carrying a specific slice of the market, allowing subscribers to consume exactly the data they need without receiving the full Currenex universe.

Messages are delivered using a Currenex-specific Itch subset with compact fixed-width binary encoding. The protocol is supported over Tcp for reliable delivery and Udp for low-latency datagram delivery on controlled networks, matching the transport options available in the companion Currenex Esp service.

### Transport

Tcp for reliable delivery of Itch Now market data messages over low-latency physical networks used by Currenex subscribers. Udp for low-latency datagram delivery of Itch Now market data on low-loss networks, with per-packet sequencing for gap detection.

### Key Characteristics

- **Forex spot market data** - Real-time prices and trades for spot currency pairs
- **Multi-feed structure** - Multiple distinct market data feeds for different slices
- **Itch encoded** - Compact fixed-width binary message format
- **Dual transport** - Tcp for reliability, Udp for low latency on controlled networks
- **Currenex platform** - Service tailored to Currenex forex subscribers

