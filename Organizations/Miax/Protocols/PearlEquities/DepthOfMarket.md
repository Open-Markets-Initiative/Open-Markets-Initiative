## PearlEquities Depth Of Market: Miax Pearl Equities Full Depth Of Book Feed

Real-time full depth of book feed publishing order events, aggregated price levels, and trade reports for Nms securities traded on the Miax Pearl Equities Exchange.

### Overview

Pearl Equities Depth Of Market is the full depth of book market data feed for the Miax Pearl Equities Exchange, publishing order-level and price-level events for every Nms security traded on the venue. The feed lets subscribers maintain a complete view of the order book, with add, modify, delete, and execute events for orders and aggregated price level changes.

Messages are distributed over Ip multicast with A and B channel redundancy, using the Miax Express binary format. Subscribers use the Miax Express Session Manager (ESesM) Tcp service for gap fill and session recovery. The feed carries trade reports, trading status, system events, and short sale price test indicators for a complete view of the Pearl Equities market.

### Transport

Udp multicast for real-time delivery of sequenced Miax Express binary depth of book messages, with primary and secondary multicast channels for redundancy. Tcp session via Miax ESesM for gap fill and recovery of messages missed on the multicast feed.

### Key Characteristics

- **Full depth of book** - Order and price level events for Nms securities
- **Miax Express** - Native binary message format for the Miax platform
- **Multicast delivery** - Udp multicast with A and B channel redundancy
- **Trade reports** - Last sale messages published alongside book updates
- **Gap fill** - Miax ESesM session for recovery of missed multicast messages
- **Trading status** - System event and instrument-level status notifications
- **Reg SHO** - Short sale price test restricted indicator updates

