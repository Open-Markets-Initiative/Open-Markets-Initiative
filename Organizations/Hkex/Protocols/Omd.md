## Omd: Hkex Orion Market Data

Binary market data protocol for disseminating real-time securities and derivatives market data from the Hong Kong Exchanges and Clearing Orion platform.

### Overview

Omd is Hkex's Orion Market Data platform for delivering real-time pricing, order book, and trade data across Hong Kong's securities and derivatives markets. The platform comprises two major feeds: Omd-C for the securities (cash) market covering equities, warrants, and structured products traded on the Stock Exchange of Hong Kong, and Omd-D for derivatives covering futures and options traded on the Hong Kong Futures Exchange.

Omd delivers full depth of book, trade tickers, market statistics, index data, and reference information through a binary message protocol optimized for low-latency consumption. The platform uses a line-based multicast architecture where instruments are assigned to channels organized by product type. Both Omd-C and Omd-D support real-time incremental updates and periodic refresh messages to enable receivers to build and maintain current market state.

### Transport

Udp multicast. Each channel provides a real-time line and a refresh line on separate multicast addresses. Packets carry sequence numbers for gap detection, and the refresh line periodically broadcasts full instrument state for recovery. Dual dissemination paths provide redundancy.

### Key Characteristics

- **Binary encoded** - Fixed-length binary messages for efficient low-latency parsing
- **Securities and derivatives** - Omd-C for cash market, Omd-D for derivatives market
- **Full depth of book** - Complete order book depth with price and aggregate quantity
- **Line-based architecture** - Instruments organized into channels with real-time and refresh lines
- **Dual dissemination** - Redundant multicast paths for failover
- **Sequence numbered** - Every packet carries sequence numbers for gap detection and recovery
