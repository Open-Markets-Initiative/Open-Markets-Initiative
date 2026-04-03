## Tops: Iex Top of Book

Market data protocol for disseminating top of book quotations and last sale information from the Investors Exchange over IexTp.

### Overview

Tops is Iex's lightweight market data feed providing best bid and offer quotations and last sale data for all securities traded on the Investors Exchange. The protocol delivers a consolidated top-of-book view with the current best bid price and size, best ask price and size, and the most recent trade for each security.

Tops is designed for applications that require current pricing without full book depth, offering a lower bandwidth alternative to the Deep feed. The feed includes trading status messages to indicate when securities are halted or paused. Tops provides an efficient real-time data stream for quote displays, alerting systems, and applications where top-of-book pricing is sufficient.

### Transport

IexTp over Udp multicast. Messages are framed within IexTp segments carrying sequence numbers, message counts, and timestamps. The transport layer provides session identification and sequencing for gap detection and recovery.

### Key Characteristics

- **Top of book** - Best bid and offer with price and size for each security
- **Last sale** - Most recent trade price, size, and sale conditions
- **IexTp transport** - Delivered over Iex Transport Protocol with sequenced Udp multicast
- **Low bandwidth** - Lightweight alternative to the full-depth Deep feed
- **Trading status** - Real-time halt, pause, and trading status notifications
- **All Iex securities** - Covers every security traded on the Investors Exchange
