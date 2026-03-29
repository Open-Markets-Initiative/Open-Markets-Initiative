## Feed: Txse Market Data

Binary market data protocol providing real-time quote and trade information for the Texas Stock Exchange.

### Overview

Feed is the Txse binary market data protocol delivering real-time order book updates, trade executions, and reference data for securities traded on the Texas Stock Exchange. The protocol uses a compact binary encoding to disseminate market events including quote updates, trade reports, auction information, and system status messages.

The protocol provides subscribers with the information needed to maintain current order book state and track trading activity. Feed is transported over the Rake session layer which provides packet framing, sequencing, and gap detection for both Tcp replay and Udp multicast delivery modes.

### Transport

Udp multicast for primary real-time delivery via the Rake framing layer. Tcp replay available for gap recovery and historical data retrieval, also over Rake.

### Key Characteristics

- **Binary encoded** - Compact binary message format for low-latency market data
- **Order book updates** - Quote additions, modifications, and deletions
- **Trade reports** - Real-time execution price and volume information
- **Rake session layer** - Framing and sequencing via the Rake protocol
- **Multicast delivery** - Udp multicast for efficient one-to-many distribution
- **Sequence numbered** - Packets carry sequence numbers for gap detection
