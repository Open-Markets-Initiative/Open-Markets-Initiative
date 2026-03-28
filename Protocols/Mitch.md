## MITCH: Millennium Exchange ITCH

Proprietary binary market data protocol developed by LSEG (London Stock Exchange Group) for Level 2 order-by-order market data dissemination on the Millennium Exchange platform, conceptually inspired by Nasdaq's ITCH protocol.

### Overview

MITCH (Millennium ITCH) is the London Stock Exchange Group's binary market data protocol for delivering Level 2 order book data. The name reflects its heritage as a protocol inspired by Nasdaq's ITCH conventions, adapted for the Millennium Exchange trading platform that LSEG acquired through its purchase of MillenniumIT in 2009. Like its Nasdaq counterpart, MITCH provides market-by-order granularity, enabling recipients to reconstruct the full state of the order book from a stream of individual order events.

MITCH underwent several iterations of improvement, including the introduction of nanosecond timestamping on all application messages and the consolidation of multiple trade-related messages into a single unified Trade message. Statistics messages were also introduced to support publication of derived market information such as opening and closing prices.

As LSEG evolved its technology, MITCH was incorporated into the broader Group Ticker Plant (GTP) architecture, which provides a consolidated market data feed across all LSEG venues. GTP carries forward the core MITCH message semantics while extending them into a unified multi-venue, multi-asset framework. Legacy MITCH feeds may still be referenced in documentation, but GTP is the current generation of LSEG market data technology.

### Transport

MITCH operates over UDP multicast. Recipients have access to two identically sequenced multicast feeds (Feed A and Feed B) for arbitration to minimize data loss. Recovery and Replay channels operate over TCP, providing retransmission of recently missed messages and full order book snapshot recovery by sending Add Order messages for every resting order on the book.

### Key Characteristics

- **Market-by-order granularity** - Full order-level detail for complete order book reconstruction
- **Binary encoding** - Compact binary message format for low-latency processing
- **Nanosecond timestamps** - All application messages carry nanosecond-precision timestamps in UTC
- **Dual-feed architecture** - Two identical multicast feeds (Feed A and Feed B) for redundancy
- **TCP recovery** - Replay for recent gaps and full snapshot recovery for larger resynchronization
- **Unidirectional** - Data flows from the exchange to subscribers (dissemination only)
- **Sequenced messages** - Sequential message numbering for gap detection
