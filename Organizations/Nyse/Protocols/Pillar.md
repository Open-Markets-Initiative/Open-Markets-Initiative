## Pillar: Nyse Trading Platform

Binary trading platform providing order entry and market data services for Nyse equities and options exchanges via the BinaryGateway interface.

### Overview

Pillar is the Nyse trading platform underpinning all Nyse Group exchanges including Nyse, Nyse Arca, Nyse American, Nyse National, and Nyse Chicago. The platform provides a unified binary protocol through the BinaryGateway interface for both order entry and market data access across equities and options instruments. Pillar replaced the legacy Nyse systems with a modern, deterministic matching engine architecture.

The BinaryGateway provides binary-encoded order entry for submitting, modifying, and cancelling orders with execution reporting, as well as market data feeds delivering real-time quotes, trades, order imbalances, and depth of book information. The platform supports multiple market models including continuous trading, auctions, and market maker quoting across all Nyse Group venues.

### Transport

Tcp for BinaryGateway order entry sessions. Multicast Udp for market data feed distribution. Binary framing with session management, sequencing, and heartbeat services.

### Key Characteristics

- **Unified platform** - Single trading technology across all Nyse Group exchanges
- **BinaryGateway** - Binary protocol for both order entry and market data
- **Equities and options** - Supports both asset classes across Nyse venues
- **Deterministic matching** - Consistent matching engine behavior across exchanges
- **Multiple market models** - Continuous trading, auctions, and market maker quoting
- **Binary encoded** - Compact binary message format for low-latency processing
