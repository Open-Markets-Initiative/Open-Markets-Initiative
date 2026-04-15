## 24XEquities Memoir Last Sale: 24X Last Sale Trade Data

Real-time trade feed reporting executions, cancellations, and corrections for securities traded on the 24X National Securities Exchange.

### Overview

Memoir Last Sale is an event-based market data protocol that publishes trade activity for every instrument traded on the 24X National Securities Exchange. The feed delivers trade reporting, trade cancellation, and trade correction events along with trading session state, enabling subscribers to consume a clean last-sale stream without needing full depth of book.

Messages are encoded using the Fix Trading Community Simple Binary Encoding standard and distributed as a sequenced fixed-width stream over the Memx-Udp multicast channel. Gap fill replay is available over the Memx-Tcp channel for subscribers that miss packets or need to resynchronize. The protocol is unidirectional and cannot be used to submit orders.

### Transport

Udp multicast via the Memx-Udp channel for real-time delivery of sequenced Sbe messages with per-message sequence numbers for gap detection. Tcp via the Memx-Tcp channel for gap fill replay when subscribers detect missed messages.

### Key Characteristics

- **Last sale** - Executed trade stream with price, size, and condition codes
- **Trade lifecycle** - Trade report, cancellation, and correction messages
- **Sbe encoded** - Fix Simple Binary Encoding for fixed-width low-latency parsing
- **Udp multicast delivery** - Real-time publication over the Memx-Udp channel with sequence numbers
- **Tcp gap fill** - Replay service over the Memx-Tcp channel for missed messages
- **Trading session status** - Current state of the trading session included in the feed
- **Unidirectional** - Market data only, cannot be used to enter orders

