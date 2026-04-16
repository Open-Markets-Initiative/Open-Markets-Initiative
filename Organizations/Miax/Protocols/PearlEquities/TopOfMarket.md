## PearlEquities Top Of Market: Miax Pearl Equities Best Bid And Offer Feed

Real-time top of market feed publishing best bid and offer quotations and trade reports for Nms securities traded on the Miax Pearl Equities Exchange.

### Overview

Pearl Equities Top Of Market is the top of book equities market data feed for the Miax Pearl Equities Exchange, publishing the best bid and best offer for every Nms security traded on the venue along with last sale trade reports. The feed uses the Miax Express binary format shared across all Miax sub-exchanges.

Messages are distributed over Ip multicast with A and B channel redundancy, and subscribers use the Miax Express Session Manager (ESesM) Tcp service for gap fill and session recovery. The feed carries quotes, trades, system events, trading status, and short sale price test restricted indicators so that subscribers can maintain a complete view of Miax Pearl Equities market state.

### Transport

Udp multicast for real-time delivery of sequenced Miax Express binary quote and trade messages, with primary and secondary multicast channels for redundancy. Tcp session via Miax ESesM for gap fill and recovery of messages missed on the multicast feed.

### Key Characteristics

- **Equities top of book** - Best bid and offer for Nms securities
- **Miax Express** - Native binary message format for the Miax platform
- **Multicast delivery** - Udp multicast with A and B channel redundancy
- **Trade reports** - Last sale messages published alongside quotes
- **Gap fill** - Miax ESesM session for recovery of missed multicast messages
- **Trading status** - System event and instrument-level status notifications
- **Reg SHO** - Short sale price test restricted indicator updates

