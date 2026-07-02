## MoonAts: OTC Markets MOON ATS data feed binary protocol

Binary multicast data feed protocol for the MOON ATS (Markets Open Overnight) NMS Overnight platform operated by OTC Markets Group. Distinct from the daytime OTC Markets ATS protocol: simpler packet flag (single Heartbeat bit; all other bits reserved), no per-message channel sequence number, and Unix-millisecond UTC timestamps for state fields.

### Overview

MOON ATS is OTC Markets Group's alternative trading system for extended overnight trading of NMS-listed US equity securities, with sessions running 18:00 to 04:00 Eastern. The MoonAts wire protocol distributes real-time order events and aggregated top-of-book quotes across two multicast channels, with a TCP-based Binary Retransmission service for recovery.

While related in shape to the daytime Otc Markets ATS protocol, the MoonAts encoding is its own binary format: the packet header's packet-flag bitmap defines only a Heartbeat bit (bits 1-7 are Reserved), messages do not carry a per-message channel sequence number, and most timestamp fields use Unix milliseconds in UTC rather than nanoseconds-since-midnight.

### Transport

UDP multicast for real-time delivery of sequenced binary order and quote messages. Separate multicast groups/ports for Top of Book and Depth of Book channels. Each packet carries a 12-byte packet header with sequence number, packet flag (heartbeat marker), message count, and packet-time-of-day milliseconds since local midnight EST/EDT. TCP Binary Retransmission service for gap recovery and on-demand snapshots. Each TCP frame is just the 3-byte message header (MessageSize + MessageType) followed by payload, framed by byte-stream reassembly using MessageSize.

### Key Characteristics

- **Overnight NMS coverage** - National Market System listed US equities traded during extended overnight session
- **Order-by-order depth** - Full order book visibility via Order Add / Update / Delete / Execution events on the DOB channel
- **Top of Book aggregation** - Aggregated best bid and offer on a dedicated TOB channel
- **A/B multicast redundancy** - Both Top of Book and Depth of Book channels are published on redundant A and B feeds
- **TCP retransmission and spin recovery** - Dedicated Binary Retransmission TCP service handles gap fills, on-demand snapshots, and spin response cycles
- **Heartbeat monitoring** - Single-bit Heartbeat flag in the UDP packet header during idle periods; periodic Heartbeat messages on the TCP recovery channel

