## Deep: Iex Full Depth of Book

Market data protocol for disseminating full depth of book, trades, auction information, and system events from the Investors Exchange over IexTp.

### Overview

Deep is Iex's comprehensive market data feed providing full order book depth, trade reports, auction details, and administrative messages for all securities traded on the Investors Exchange. The protocol delivers price level aggregated book updates on both the bid and ask sides, enabling subscribers to reconstruct the complete visible order book at every price level on the exchange.

In addition to order book depth, Deep carries trade messages with price, size, and sale condition information, as well as official price messages for opening and closing auctions. The feed includes security directory, trading status, and halt information to provide a complete picture of market state. Deep builds upon the simpler Tops feed by adding full book depth and additional message types.

### Transport

IexTp over Udp multicast. Messages are framed within IexTp segments carrying sequence numbers, message counts, and timestamps. The transport layer provides session identification and sequencing for gap detection and recovery.

### Key Characteristics

- **Full depth of book** - Complete price level aggregated order book on both sides
- **Trade reports** - Last sale data with price, size, and sale conditions
- **Auction information** - Opening and closing auction details and official prices
- **IexTp transport** - Delivered over Iex Transport Protocol with sequenced Udp multicast
- **Security directory** - Reference data for all traded securities
- **Trading status** - Real-time halt, pause, and trading status notifications
