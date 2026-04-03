## Xmt: eXtreme Message Transfer Protocol

Proprietary binary protocol developed by Tmx Group for high-performance equities market data dissemination on Tsx and Tsxv.

### Overview

Xmt (eXtreme Message Transfer Protocol) is a binary market data protocol designed for low-latency delivery of equities trading information. It serves as the primary Level 2 market data feed for the Toronto Stock Exchange (Tsx) and Tsx Venture Exchange (Tsxv), providing real-time order book and trade data to market participants.

The protocol provides full depth of book with order-by-order visibility, trade reports, instrument reference data, and market state updates. Xmt supports multicast delivery for efficient distribution to subscribers.

### Transport

Udp multicast. Messages carry sequence numbers for gap detection and recovery.

### Key Characteristics

- **Equities focused** - Purpose-built for Tsx and Tsxv equity market data
- **Binary encoding** - Compact binary message format optimized for parsing speed
- **Depth of book** - Level 2 order book data with full price depth
- **Low latency** - Designed for minimal wire-to-parse latency
- **Sequenced delivery** - Sequence numbers for gap detection and recovery
