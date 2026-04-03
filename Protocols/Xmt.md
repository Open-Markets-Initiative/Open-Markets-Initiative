## XMT: eXtreme Message Transfer Protocol

Proprietary binary protocol developed by TMX Group and licensed to several exchanges for high-performance equities market data dissemination.

### Overview

XMT (eXtreme Message Transfer Protocol) is a binary market data protocol designed for low-latency delivery of equities trading information. It serves as the primary market data feed for TSX and TSXV (TSX Venture Exchange), providing real-time Level 2 order book and trade data to market participants.

The protocol provides full depth of book with order-by-order visibility, trade reports, instrument reference data, and market state updates. XMT supports multicast delivery for efficient distribution to a large number of subscribers simultaneously.

### Transport

XMT operates over both TCP and UDP, supporting multicast delivery for efficient distribution of market data to a large number of subscribers. Messages carry sequence numbers for gap detection and recovery.

### Key Characteristics

- **Equities focused** - Purpose-built for equity market data on TSX and TSXV
- **Binary encoding** - Compact binary message format optimized for parsing speed
- **Depth of book** - Provides Level 2 order book data with full price depth
- **Low latency** - Designed for minimal wire-to-parse latency
- **Sequenced delivery** - Messages carry sequence numbers for gap detection and recovery
