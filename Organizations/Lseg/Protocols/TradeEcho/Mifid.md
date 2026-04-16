## TradeEcho Mifid: Lseg Trade Echo Mifid Post Trade Data

MiFID II post-trade transparency feed published via the Lseg Trade Echo service.

### Overview

Trade Echo MiFID II Post Trade is a market data feed from the Lseg Trade Echo service, delivered via the Lseg Group Ticker Plant (Gtp) binary format over Ip multicast. Trade Echo provides a consolidated view across Lseg venues.

### Transport

Udp multicast via the Lseg Group Ticker Plant (Gtp) framing for real-time delivery of sequenced binary messages. Tcp for the Gtp retransmission and snapshot services for recovery of missed multicast messages.

### Key Characteristics

- **Trade Echo** - Consolidated market data service across Lseg venues
- **Gtp format** - Lseg Group Ticker Plant binary encoding
- **Multicast delivery** - Udp multicast with sequence numbers
- **Gap recovery** - Tcp retransmission and snapshot services

