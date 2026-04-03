## Bbds: Finra Bulletin Board Dissemination Service

Market data protocol for disseminating Otcbb quotation data for bulletin board securities over MoldUdp64 multicast.

### Overview

Bbds is Finra's Bulletin Board Dissemination Service for distributing real-time quotation information for Otcbb securities. The protocol delivers bid and ask quotes, quote updates, and market maker identification for securities quoted on the Otc Bulletin Board. Bbds provides market participants with current quotation activity from registered market makers in Otcbb-eligible securities.

The service carries quote messages including price levels, sizes, and market maker identifiers, enabling subscribers to construct and maintain a current view of the Otcbb quotation montage. Bbds supports quote updates, withdrawals, and status changes to reflect the evolving state of market maker interest throughout the trading day.

### Transport

MoldUdp64 multicast. Messages are sequenced and delivered over Udp multicast with MoldUdp64 framing, providing session identification, sequence numbering, and message count per packet for gap detection and recovery.

### Key Characteristics

- **Otcbb quotations** - Real-time dissemination of bulletin board security quotes
- **MoldUdp64 transport** - Sequenced multicast delivery with gap detection support
- **Market maker identified** - Quotes attributed to individual registered market makers
- **Bid and ask data** - Provides price and size for both sides of the quotation
- **Quote lifecycle** - Supports new quotes, updates, and withdrawals
- **Montage construction** - Enables building a full market maker quotation display
