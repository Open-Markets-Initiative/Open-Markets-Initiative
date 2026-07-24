## Omdcc: Orion Market Data China Connect

Binary market data dissemination platform for the Hkex Northbound Stock Connect programme. OMD-CC delivers real-time market data for eligible A-Share securities traded on the Shanghai Stock Exchange (SSE) and Shenzhen Stock Exchange (SZSE) that are accessible via Stock Connect. Each market is disseminated on its own set of dedicated multicast channels sharing a common binary wire format.

### Overview

OMD-CC is the China Connect variant of the Hkex Orion Market Data platform. Its packet header is the same 16-byte structure used by OMD-C (Securities): PktSize, MsgCount, Filler, SeqNum, SendTime — with a plain filler byte at offset 3 (no payload compression). Message content is scoped to Stock Connect eligibility: Market Definition, Security Definition, Security Status, Top Of Book, and Statistics.

SSE and SZSE are transmitted on separate multicast channels but share an identical wire format. The MarketCode field within each message distinguishes ASHR (SSE A-Share) from ASZR (SZSE A-Share). Recovery uses the same dual-channel arbitration, TCP retransmission, and UDP refresh channels as OMD-C.

### Transport

OMD-CC distributes all real-time market data via UDP multicast with dual A/B channels and per-channel sequence numbers. A dedicated DR Signal multicast channel broadcasts failover activation and completion.

### Key Characteristics

- **Binary little-endian** - Compact binary format with little-endian byte order
- **16-byte packet header** - Same layout as OMD-C: PktSize, MsgCount, Filler, SeqNum, SendTime (no compression byte)
- **Northbound Stock Connect scope** - Covers SSE A-Share and SZSE A-Share securities accessible via Stock Connect
- **UDP multicast delivery** - One-to-many distribution with dual A/B channel redundancy per market
- **Top-of-book market data** - Publishes best bid/ask price and aggregate quantity, security definitions, status, and statistics
- **TCP retransmission + UDP refresh** - Same recovery mechanisms as OMD-C

