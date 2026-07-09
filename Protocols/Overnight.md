## Overnight: OTC Link Overnight OTC Inter-dealer Quotation System (IDQS) binary market-data protocol

Binary multicast data feed protocol for the OTC Link Overnight OTC Inter-dealer Quotation System (IDQS) operated by OTC Markets Group. Distributes overnight quotation and order data for OTC equities during the extended 18:00 to 07:45 Eastern session. Shares wire framing shape with the MOON ATS encoding (12-byte packet header, 3-byte message header, order-based message set at codes 9/11/12/20-28 plus ASCII TCP-retransmission session), but is a separately-branded protocol serving the OTC dealer-quoted market rather than MOON's NMS overnight ATS.

### Overview

OTC Overnight is OTC Markets Group's overnight quotation platform for OTC equities, running an Inter-dealer Quotation System (IDQS) from 18:00 Eastern to 07:45 Eastern. The wire protocol distributes order-by-order depth events and aggregated top-of-book quotes across two multicast channels, with a TCP-based Binary Retransmission service for gap-fill and snapshot recovery.

The wire framing (packet header, message header, message type numbering) matches the MOON ATS binary protocol used for NMS overnight trading, but the two are distinct products with different market rules, different session hours (Overnight closes 07:45 AM vs MOON's 04:00 AM), different Trading Session enum values (7:00 PM order acceptance vs MOON's 7:30 PM), and a full nine-value Tier enum (No Tier, OTCQX US, OTCQX International, OTCQB, OTCID, Pink Limited, Grey Market, Expert Market, OTC Bonds) reflecting the OTC dealer market's tiered symbols.

### Transport

UDP multicast for real-time delivery of sequenced binary order and quote messages. Separate multicast groups for Top of Book and Depth of Book channels, each published on redundant A and B feeds. Each packet carries a 12-byte packet header with sequence number, single-bit Heartbeat flag, message count, and packet-time-of-day milliseconds since local midnight EST/EDT. TCP Binary Retransmission service for gap recovery and on-demand snapshots. Session-based flow: Login, Retransmission Request/Response, Spin Request/Response, Enhanced Spin Request/Response, Heartbeat. Each TCP frame is a 3-byte message header (MessageSize + MessageType) followed by payload, framed by byte-stream reassembly using MessageSize.

### Key Characteristics

- **OTC dealer market coverage** - Overnight quotation and trading for OTC equities across the full tier structure (OTCQX, OTCQB, OTCID, Pink, Grey, Expert Market, OTC Bonds)
- **Order-by-order depth** - Full order book visibility via Order Add / Update / Delete / Execution events on the DOB channel
- **Top of Book aggregation** - Aggregated best bid and offer on a dedicated TOB channel
- **A/B multicast redundancy** - Both Top of Book and Depth of Book channels are published on redundant A and B feeds
- **Extended overnight session** - Application up from 18:00 Eastern to 07:45 Eastern; Order Acceptance at 19:00, Market Open at 20:00, Market Close at 07:45
- **TCP retransmission and spin recovery** - Session-based TCP Binary Retransmission service handles gap fills, on-demand snapshots, and spin/enhanced-spin response cycles
- **Heartbeat monitoring** - Single-bit Heartbeat flag in the UDP packet header during idle periods; periodic Heartbeat messages on the TCP recovery channel

