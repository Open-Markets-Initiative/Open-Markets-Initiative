## TradeEcho Level2: Lseg Trade Echo Depth Of Book Data

Level 2 depth of book feed published via the Trade Echo service for securities traded on Lseg venues.

### Overview

Trade Echo Level 2 is a market data feed from the Lseg Trade Echo service, delivered via the Lseg Group Ticker Plant (Gtp) binary format over Ip multicast. Trade Echo provides a consolidated view across Lseg venues.

### Transport

Udp multicast via the Lseg Group Ticker Plant (Gtp) framing for real-time delivery of sequenced binary messages. Tcp for the Gtp retransmission and snapshot services for recovery of missed multicast messages.

### Key Characteristics

- **Trade Echo** - Consolidated market data service across Lseg venues
- **Gtp format** - Lseg Group Ticker Plant binary encoding
- **Multicast delivery** - Udp multicast with sequence numbers
- **Gap recovery** - Tcp retransmission and snapshot services

