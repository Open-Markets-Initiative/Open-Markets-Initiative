## Atds: Finra Agency Debt Trade Dissemination Service

Market data protocol for disseminating Trace agency debt trade reports in real time over MoldUdp64 multicast.

### Overview

Atds is Finra's Agency Debt Trade Dissemination Service for distributing real-time trade information for agency debt securities reported through the Trace system. The protocol carries trade reports for agency debentures, agency mortgage-backed securities, and other agency debt instruments, providing transparency into fixed income transaction activity.

The service disseminates trade price, yield, volume, and execution details as they are reported and validated through Trace. Atds supports trade corrections, cancellations, and reversals to maintain an accurate record of agency debt market activity. The protocol enables market participants to monitor real-time transaction flow in the agency debt market.

### Transport

MoldUdp64 multicast. Messages are sequenced and delivered over Udp multicast with MoldUdp64 framing, providing session identification, sequence numbering, and message count per packet for gap detection and recovery.

### Key Characteristics

- **Trace agency debt trades** - Real-time dissemination of agency debt transaction reports
- **MoldUdp64 transport** - Sequenced multicast delivery with gap detection support
- **Yield and price data** - Provides both price and yield information for debt instruments
- **Corrections and reversals** - Supports trade report amendments after initial publication
- **Agency debt coverage** - Covers agency debentures, mortgage-backed, and related securities
- **Execution details** - Includes trade size, execution time, and reporting party information
