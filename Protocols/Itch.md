## Itch: Integrated Trading Channel Handlers

Nasdaq Itch market data protocol a sequenced binary wire format distributing full order book add, modify, cancel, execute, and trade messages for Nasdaq listed securities and licensed to many global venues.

### Overview

ITCH is a direct data-feed protocol designed for high-performance market data delivery. It provides a full order-by-order view of the order book, enabling subscribers to reconstruct the complete state of the market at any point in time. Each message reflects an individual order event such as an add, modify, cancel, or execution, offering the highest granularity of market data available from ITCH-based venues.

Originally developed by Nasdaq for its US equity exchanges, ITCH has been widely licensed and adopted by exchanges globally including ASX, Japannext, Cboe FX, Odx, and others. The protocol is typically paired with OUCH for order entry and transported over MoldUDP or SoupBinTCP session layers depending on the delivery mechanism.

### Transport

ITCH operates over both TCP and UDP depending on the exchange implementation. Multicast UDP via MoldUDP64 is the most common transport for real-time market data distribution. Messages are sequenced, allowing subscribers to detect gaps and recover missed data through retransmission services.

### Key Characteristics

- **Full depth of book** - Provides every order add, modify, cancel, and execution event
- **Sequenced messages** - Each message carries a sequence number for gap detection and recovery
- **Unidirectional** - Data flows from the exchange to the subscriber (dissemination only)
- **Binary encoding** - Fixed-length fields with big-endian byte ordering for efficient parsing
- **High throughput** - Designed for millions of messages per second during peak market activity

