## AMD: Aquis Market Data

Proprietary binary protocol developed by Aquis Exchange for real-time market data dissemination, used on Aquis Exchange venues in the UK and EU as well as A2X Markets in South Africa.

### Overview

Aquis Market Data (AMD) is a binary market data protocol that delivers real-time order and trade information from Aquis Exchange matching engines to market data subscribers. The protocol provides continuous order-by-order and aggregated book feeds throughout the trading day, enabling participants to reconstruct the full state of the order book.

Aquis Exchange operates multilateral trading facilities (MTFs) in the UK and EU, and has licensed its exchange technology platform to A2X Markets, the South African equities exchange. Both venues use the same underlying protocol for market data distribution, providing a consistent interface for firms connected to multiple Aquis-powered venues.

The AMD protocol is complemented by snapshot feeds that publish order book data at regular intervals, and a TCP/IP replay service that allows recipients to recover specific messages missed from the continuous multicast feed.

### Transport

AMD operates over IP multicast (UDP) for real-time market data distribution. Multiple multicast groups carry different feed types including order feeds, trade feeds, and snapshot feeds. A TCP/IP-based replay service provides message recovery for subscribers that detect sequence gaps in the multicast stream. Messages use binary encoding with 1-byte packing and little-endian integer representation for efficient parsing.

### Key Characteristics

- **Binary encoding** - Fixed-length binary messages with little-endian byte ordering and 1-byte packing
- **Multicast delivery** - Real-time data distributed via IP multicast UDP feeds
- **Sequenced messages** - Messages carry sequence numbers for gap detection and recovery
- **Replay service** - TCP/IP recovery service for retransmission of missed messages
- **Order-by-order depth** - Provides full order book visibility with individual order events
- **Snapshot feeds** - Periodic order book snapshots for initial book construction