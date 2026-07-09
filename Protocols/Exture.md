## Exture: Koscom MDCS Exture 3.0 ASCII fixed-width UDP multicast market data protocol

Exture is the ASCII fixed-width market data protocol used by Koscom's Market Data Service (MDCS) to disseminate KRX real-time market data. Each UDP multicast datagram carries one Exture record: 2 bytes ASCII Data Category, 3 bytes ASCII Information Category, variable-length ASCII payload, and a single 0xFF end-of-text sentinel byte. Numeric fields are encoded as ASCII digit runs with implied decimal places carried in the specification.

### Overview

Exture is the third-generation KRX Next Generation System market data protocol, developed by Koscom (Korea Securities Computing Corporation) to replace earlier KRX dissemination formats. It uses printable ASCII text on the wire so consumers can inspect payloads without a binary decoder. Every field has a fixed byte width; numeric fields are right-justified zero-padded or left-justified space-padded per SPEC Details conventions.

Message dispatch is by TR-CODE, formed by concatenating a 2-character Data Category (message family — Quote, Snapshot, Order Filled, Batch Data, Index, etc.) with a 3-character Information Category (market/product variant — 01S for KOSPI Equities, 01F for Derivatives, 01B for Bonds, 000 for market-independent). Numeric fields marked Double or FLOAT128 carry implied decimal places determined by the DecimalPlaces column of the specification.

Content spans KRX venues: KOSPI, KOSDAQ, KONEX equities; K200/KOSDAQ150/Equity/KTB/Currency/Commodity futures and options; General/Baby Bonds; REPO; Spot Gold; Emissions; K-OTC; plus KRX Index and Koscom-originated third-party bond/equity indices (MKF, KIS, KEBI, KABI, NicePNI, WISEfn).

### Transport

Exture records are disseminated as ASCII fixed-width UDP multicast datagrams. Each datagram contains exactly one message. The first 5 ASCII bytes form the TR-CODE (Data Category + Information Category) that discriminates message type. The final byte is a 0xFF end-of-text sentinel. Retransmission is available on separate TCP/UDP recovery ports.

### Key Characteristics

- **ASCII fixed-width** - All fields encoded as printable ASCII; numeric fields are digit runs with implied decimal places carried in the spec
- **Two-level TR-CODE dispatch** - 5-byte TR-CODE = 2-byte Data Category (family) + 3-byte Information Category (market/product variant)
- **UDP multicast** - One message per UDP datagram; ports and multicast groups partition streams by subscription product (Securities A/B/C, Bond A, Derivatives A, Commodities, Index Products 1/2/3, Koscom, etc.)
- **0xFF end-of-text sentinel** - Every record ends with a single 0xFF byte marking the end of message payload
- **Line-tier bandwidth model** - Same content offered at multiple line-speed tiers (100M, 12M, 45M, 8M, 512K); customers subscribe by tier
- **Koscom MDCS distribution** - Distributed by Koscom (KRX-owned) via the MDCS portal at data.koscom.co.kr

