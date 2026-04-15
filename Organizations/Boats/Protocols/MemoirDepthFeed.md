## Memoir Depth Feed: Boats Depth Of Book Data

Real-time depth of book feed providing order data, non-displayed trade information, and trading session status for securities traded on Blue Ocean Ats.

### Overview

Memoir Depth Feed is an event-based market data protocol that publishes the complete displayed order book for every instrument traded on Blue Ocean Ats. The feed delivers order add, modify, and delete events, non-displayed trade information, trading session state, and trading action notifications, allowing subscribers to reconstruct and maintain full order book state during overnight sessions.

Messages are encoded using the Fix Trading Community Simple Binary Encoding standard and distributed as a sequenced fixed-width stream over the Memx-Udp multicast channel. Gap fill replay is available over the Memx-Tcp channel for subscribers that miss packets or need to resynchronize. The protocol is unidirectional and cannot be used to submit orders.

### Transport

Udp multicast via the Memx-Udp channel for real-time delivery of sequenced Sbe messages with per-message sequence numbers for gap detection. Tcp via the Memx-Tcp channel for gap fill replay when subscribers detect missed messages.

### Key Characteristics

- **Full depth of book** - Every displayed order visible at every price level
- **Sbe encoded** - Fix Simple Binary Encoding for fixed-width low-latency parsing
- **Udp multicast delivery** - Real-time publication over the Memx-Udp channel with sequence numbers
- **Tcp gap fill** - Replay service over the Memx-Tcp channel for missed messages
- **Order-level events** - Add, modify, and delete messages for individual orders
- **Non-displayed trades** - Execution reports for hidden liquidity
- **Trading actions** - Per-instrument trading status and session state notifications
- **Unidirectional** - Market data only, cannot be used to enter orders

