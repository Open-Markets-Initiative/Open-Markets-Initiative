## Cqs: Consolidated Quotation System

Consolidated market data protocol disseminating best bid and offer quotes from all Us equity exchanges and market makers.

### Overview

The Consolidated Quotation System (Cqs) is the Siac-operated national market data feed providing real-time best bid and offer quotes for all Nms-listed equity securities. Cqs collects quotation data from all participating Us equity exchanges and Finra and disseminates consolidated best bid and offer information to subscribers. The feed serves as the authoritative source for the National Best Bid and Offer (Nbbo).

Cqs operates in both input and output directions. The input side receives quote updates from participating exchanges and market centers, while the output side disseminates consolidated quotation data to market data subscribers. The protocol carries quote messages with price, size, exchange identification, and condition indicators for each security.

### Transport

Multicast Udp for output distribution. Dedicated connections for input submission from participating exchanges. Sequenced delivery with gap detection and retransmission capabilities.

### Key Characteristics

- **Consolidated quotes** - Best bid and offer from all Us equity exchanges
- **Nbbo source** - Authoritative National Best Bid and Offer calculation
- **Input and output** - Bidirectional quote collection and dissemination
- **All Nms securities** - Covers all national market system listed equities
- **Exchange attribution** - Quote source identification per exchange
- **Regulatory feed** - Sip-operated feed mandated by Regulation Nms
