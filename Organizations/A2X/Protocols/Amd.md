## Amd: A2X Aquis Market Data

Binary market data protocol for disseminating real-time pricing and order book data on the A2X Markets exchange using Aquis technology.

### Overview

Amd is the market data protocol used by A2X Markets to deliver real-time order book and trade data for equities listed on the South African exchange. The protocol is based on Aquis Exchange technology, providing a proven binary market data dissemination platform.

Amd delivers incremental order book updates, trade reports, and instrument reference data to subscribers. The feed supports full depth of book visibility with add, modify, and delete messages for maintaining an accurate view of the order book state across all listed instruments.

### Transport

Udp multicast. Real-time market data is disseminated on multicast groups with sequence numbers for gap detection and message ordering.

### Key Characteristics

- **Aquis technology** - Built on the proven Aquis Exchange market data platform
- **Binary encoded** - Efficient binary message format for low-latency processing
- **Full depth of book** - Order book updates at every price level
- **Incremental updates** - Real-time add, modify, and delete messages for book maintenance
- **Sequence numbered** - Packets carry sequence numbers for gap detection
