## Ats: OTC Markets ATS Protocol

Proprietary multicast data feed protocol developed by OTC Markets Group for real-time dissemination of OTC equity market data from its Alternative Trading System platforms.

### Overview

The OTC Markets ATS Protocol is a binary multicast data feed specification used by OTC Markets Group to distribute real-time quote, order, and trade data from its trading venues. OTC Markets Group operates OTC Link ATS and OTC Link ECN for trading in OTC equities, and the MOON ATS (Markets Open Overnight) platform for extended-hours trading.

The protocol delivers multiple market data products including order-by-order depth feeds, aggregated Top of Book feeds, and trade reporting data. Subscribers can reconstruct the full state of the order book from the continuous message stream.

Since multicast UDP distribution is inherently unreliable, the protocol includes a TCP-based recovery mechanism. When a subscriber detects a message gap through sequence number monitoring, it initiates a TCP connection to a Recovery Server to request retransmission of missed messages.

### Transport

The protocol operates over UDP multicast for real-time data distribution. Each UDP packet contains a packet header indicating the message type (heartbeat, sequence number reset, or data). A TCP-based Recovery Server provides gap-fill retransmission when subscribers detect missed messages. Heartbeat packets are sent during periods of inactivity.

### Key Characteristics

- **UDP multicast delivery** - Real-time distribution via multicast groups
- **Sequenced messages** - Sequence numbers for gap detection across feeds
- **TCP recovery** - Dedicated Recovery Server for retransmission of missed messages
- **Order-by-order depth** - Full order book visibility with individual order events
- **Top of Book aggregation** - Aggregated best bid and offer feeds
- **Heartbeat monitoring** - Periodic heartbeats during idle periods for connection health

