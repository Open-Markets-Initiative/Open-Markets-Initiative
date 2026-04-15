## Broadcast Feed: Tmx Toronto Stock Exchange Broadcast Market Data

Market data feed publishing real-time quotes and trades for securities traded on the Tmx Toronto Stock Exchange and Tsx Venture Exchange.

### Overview

Broadcast Feed is the real-time market data product for the Tmx Toronto Stock Exchange (Tsx) and Tsx Venture Exchange, publishing quote updates, trade reports, and session events for every listed security. It is the primary data feed for subscribers tracking Canadian cash equities markets.

### Transport

Udp multicast via the Sola transport framing for real-time delivery of sequenced messages with per-packet sequence numbers for gap detection. Tcp for the Sola gap fill and retransmission services used by subscribers to recover missed multicast messages.

### Key Characteristics

- **Tsx and Tsxv** - Coverage of Toronto Stock Exchange and Tsx Venture
- **Multicast delivery** - Real-time Udp multicast distribution
- **Quote and trade events** - Real-time updates for listed securities
- **Gap recovery** - Tcp gap fill and retransmission service
- **Binary encoded** - Compact fixed-width binary messages

