## Market Data: Ndfex Equities Market Data Feed

Binary market data feed publishing real-time order book, trade, and reference data for equities traded on the Ndfex exchange.

### Overview

Ndfex Market Data is the real-time market data feed for the Ndfex exchange, distributing order book events, trade reports, and reference data for listed equities. The protocol uses the Obp binary encoding for compact fixed-width messages.

### Transport

Udp multicast for real-time delivery of sequenced binary order book and trade messages with per-packet sequence numbers. Tcp for the replay service for recovery of messages missed on the multicast feed.

### Key Characteristics

- **Ndfex market data** - Real-time equities market data
- **Obp encoded** - Binary message encoding
- **Multicast delivery** - Udp multicast with sequence numbers
- **Replay service** - Tcp recovery for missed messages
- **Reference data** - Instrument definitions in the feed

