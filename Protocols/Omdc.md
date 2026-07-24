## Omdc: Orion Market Data Cash

Binary market data dissemination platform for the Hkex Securities Market covering equities, warrants, CBBCs, ETFs, REITs, bonds, and structured products. OMD-C delivers depth-of-book, trades, reference data, and third-party indices via Ip multicast with dual-channel redundancy. Tiered as SS (Standard), SP (Premium), SF (FullTick), and Index datafeeds.

### Overview

OMD-C is the securities-market variant of the Hkex Orion Market Data platform. Its packet header is a 16-byte fixed structure carrying packet size, message count, a filler byte, sequence number, and send time (nanoseconds since Unix epoch with millisecond precision). Each subsequent message uses a 4-byte header of message size + message type before its body. OMD-C does not use payload compression; the byte at packet-header offset 3 is a Filler, distinguishing OMD-C from OMD-D which places a Compression Mode indicator at the same offset.

The four OMD-C datafeed tiers subset the same wire format: SS carries aggregate depth + broker queue + trade tickers + statistics; SP carries aggregate depth + per-trade granularity; SF carries full order-level events + per-trade granularity; Index publishes third-party index definitions and values. Complementary feeds (Odd Lot Order, Conflated Broker Queue, Stock Connect Northbound Daily Quota) are distributed alongside the four main tiers.

### Transport

OMD-C distributes all market data via UDP multicast. Each data feed is assigned dedicated multicast groups organized by market segment and data type. Messages are duplicated across two independent multicast channels (Line A and Line B). Each channel maintains its own session with strictly increasing sequence numbers for gap detection. A TCP retransmission service allows clients to request specific missed messages. A dedicated DR Signal multicast channel broadcasts failover activation and completion notifications.

### Key Characteristics

- **Binary little-endian** - Compact binary format with little-endian byte order for signed and unsigned integers
- **16-byte packet header** - PktSize, MsgCount, Filler, SeqNum, SendTime (no compression byte)
- **UDP multicast delivery** - One-to-many distribution over IP multicast for efficient bandwidth utilization
- **Dual-channel redundancy** - Every message sent on two independent multicast lines (Line A / Line B)
- **Sequence-numbered messages** - Strictly increasing per-channel sequence numbers for gap detection
- **TCP retransmission** - Unicast recovery service for requesting missed messages by sequence number
- **Disaster recovery signaling** - Dedicated multicast channel for site failover notifications
- **No payload compression** - OMD-C does not compress payload messages; byte 3 of the packet header is a plain filler

