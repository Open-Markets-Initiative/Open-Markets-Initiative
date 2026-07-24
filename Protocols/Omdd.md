## Omdd: Orion Market Data Derivatives

Binary market data dissemination platform for the Hkex Derivatives Market covering stock and index futures and options, interest-rate and fixed-income futures, commodity, currency, and gold futures. OMD-D delivers order book, trades, calculated opening prices, implied volatility, open interest, and market alerts via Ip multicast with dual-channel redundancy. Supports optional payload compression signalled at the packet header. Tiered as DS (Standard), DP (Premium), DF (FullTick), D-Lite, and Combined datafeeds.

### Overview

OMD-D is the derivatives-market variant of the Hkex Orion Market Data platform. Its packet header is a 16-byte fixed structure carrying packet size, message count, a Compression Mode indicator (byte 3), sequence number, and send time (nanoseconds since Unix epoch). Compression Mode distinguishes OMD-D from OMD-C, which uses a plain Filler byte at the same offset because it does not support payload compression.

The OMD-D v2.x wire format (Orion Derivatives Platform / ODP) added additional message types (Aggregate Implied Order, Modify Order, Delete Order) and reorganised several structures relative to v1.x. Consumers of OMD-D typically build the full derivatives limit order book from the stream of Add / Modify / Delete Order events; auction opening prices, implied volatility, open interest, and market alerts are published as separate message types on the same multicast fabric.

### Transport

OMD-D distributes market data via UDP multicast with dual A/B channels and per-channel sequence numbers. A TCP retransmission service allows clients to request missed messages, and a dedicated DR Signal multicast channel broadcasts failover activation and completion notifications.

### Key Characteristics

- **Binary little-endian** - Compact binary format with little-endian byte order for signed and unsigned integers
- **16-byte packet header** - PktSize, MsgCount, CompressionMode, SeqNum, SendTime
- **Payload compression supported** - Byte 3 of the packet header signals whether the payload messages are compressed
- **UDP multicast delivery** - One-to-many distribution over IP multicast for efficient bandwidth utilization
- **Dual-channel redundancy** - Every message sent on two independent multicast lines (Line A / Line B)
- **Sequence-numbered messages** - Strictly increasing per-channel sequence numbers for gap detection
- **TCP retransmission** - Unicast recovery service for requesting missed messages by sequence number
- **Disaster recovery signaling** - Dedicated multicast channel for site failover notifications

