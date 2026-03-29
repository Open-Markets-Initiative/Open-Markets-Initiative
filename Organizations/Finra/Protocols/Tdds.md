## Tdds: Finra Trade Data Dissemination Service

Market data protocol for disseminating Otc equity trade reports from the Orf reporting facility in real time over MoldUdp64 multicast.

### Overview

Tdds is Finra's Trade Data Dissemination Service for distributing real-time trade information for Otc equity securities. The protocol carries trade reports originating from the Otc Reporting Facility (Orf), providing last sale data for Otc equities that do not trade on a listed exchange. Tdds delivers trade price, volume, and condition information to market data consumers.

The service disseminates trade events as they are reported and validated, enabling market participants to track Otc equity transaction activity. Tdds supports trade corrections, cancellations, and as-of trades to maintain an accurate consolidated view of Otc equity market activity throughout the trading session.

### Transport

MoldUdp64 multicast. Messages are sequenced and delivered over Udp multicast with MoldUdp64 framing, providing session identification, sequence numbering, and message count per packet for gap detection and recovery.

### Key Characteristics

- **Otc equity trades** - Real-time dissemination of Otc Reporting Facility trade reports
- **MoldUdp64 transport** - Sequenced multicast delivery with gap detection support
- **Trade conditions** - Includes sale condition modifiers and settlement terms
- **Corrections and cancellations** - Supports trade report amendments after initial publication
- **Last sale data** - Provides price, volume, and timestamp for each reported trade
- **As-of trades** - Handles late-reported trades with original execution timestamps
