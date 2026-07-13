## Overnight Depth Of Book: Order-by-order full depth channel for OTC Link Overnight OTC

Order-by-order market data channel publishing full depth events (Order Add, Order Update, Order Delete, Order Execution, Order Execution with Price, Order Flag, Trade, Imbalance) plus session lifecycle (Start of Spin, End of Spin, Trading Session) and security reference (Security, Security Flag) messages. Used by OTC Link Overnight OTC, the overnight quotation platform for OTC equities; each subscriber can reconstruct the full order book from the sequenced event stream.

### Overview

OTC Depth of Book is the order-by-order channel of the OTC extended-hours market data feeds. It publishes individual order events (add/update/delete/execution) allowing subscribers to reconstruct the full order book. Used by OTC Link Overnight OTC for overnight OTC dealer-quoted equities; the platform runs an Inter-dealer Quotation System from 18:00 to 07:45 Eastern.

Session lifecycle is signaled by Start of Spin / End of Spin messages that bracket the initial security list and by Trading Session messages that mark session-time transitions. Recovery is via A/B feed arbitration during runtime plus a companion Retransmission TCP service for gap fills and spin-based snapshot recovery.

### Transport

UDP multicast for real-time delivery of sequenced binary order events. Each packet carries a 12-byte packet header (sequence number, packet flag, message count, packet time-of-day) followed by concatenated messages framed by a 3-byte message header (MessageSize + MessageType). Redundant A/B multicast feeds for arbitration.

### Key Characteristics

- **Order-by-order depth** - Full order book reconstruction from Order Add / Update / Delete / Execution events
- **Overnight coverage** - OTC Link Overnight OTC session (18:00 to 07:45 Eastern)
- **Spin-bracketed sessions** - Start of Spin / End of Spin messages delineate session initialization and closure
- **Trade and imbalance events** - Non-displayed liquidity trade reports plus periodic order imbalance dissemination
- **A/B multicast redundancy** - Redundant A and B feeds published in parallel for arbitration and gap detection
- **Companion retransmission service** - Recovery via the Retransmission TCP channel for gap fills and spin snapshot recovery

