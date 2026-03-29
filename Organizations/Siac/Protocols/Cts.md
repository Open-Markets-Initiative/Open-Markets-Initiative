## Cts: Consolidated Tape System

Consolidated market data protocol disseminating last sale trade reports from all Us equity exchanges and trade reporting facilities.

### Overview

The Consolidated Tape System (Cts) is the Siac-operated national market data feed providing real-time last sale trade reports for all Nms-listed equity securities. Cts collects trade execution data from all participating Us equity exchanges and Finra trade reporting facilities and disseminates consolidated trade information to subscribers.

Cts operates in both input and output directions. The input side receives trade reports from participating exchanges and trade reporting facilities, while the output side disseminates consolidated last sale data to market data subscribers. The protocol carries trade messages with execution price, volume, exchange identification, sale conditions, and timestamps for each reported transaction.

### Transport

Multicast Udp for output distribution. Dedicated connections for input submission from participating exchanges and trade reporting facilities. Sequenced delivery with gap detection.

### Key Characteristics

- **Consolidated trades** - Last sale reports from all Us equity exchanges
- **Input and output** - Bidirectional trade collection and dissemination
- **All Nms securities** - Covers all national market system listed equities
- **Sale conditions** - Trade condition indicators for each execution
- **Exchange attribution** - Trade source identification per reporting venue
- **Regulatory feed** - Sip-operated feed mandated by Regulation Nms
