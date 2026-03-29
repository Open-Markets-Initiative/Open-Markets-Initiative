## Memoir Top: Memx Top of Book

Sbe-encoded market data protocol providing top of book quotes for equities and options traded on Memx.

### Overview

Memoir Top is the Memx top of book market data feed delivering real-time best bid and offer updates for equities and options instruments. The protocol uses Simple Binary Encoding (Sbe) to provide a lightweight, low-bandwidth alternative to the full depth Memoir Depth feed, disseminating only the current best bid price, best offer price, and associated sizes.

The feed is designed for participants who require current best quote information without the overhead of maintaining a full order book. Memoir Top covers both equities and options instruments on the Memx exchange, providing efficient price discovery for routing decisions, display applications, and compliance monitoring.

### Transport

Udp multicast with sequenced packets. Gap detection via sequence numbers with snapshot recovery for quote state synchronization.

### Key Characteristics

- **Sbe encoded** - Fixed-position, fixed-length fields for zero-copy parsing
- **Top of book** - Best bid and offer with associated sizes
- **Equities and options** - Covers both asset classes on Memx
- **Low bandwidth** - Compact messages compared to full depth feeds
- **Multicast delivery** - Udp multicast for efficient one-to-many distribution
- **Sequence numbered** - Packets carry sequence numbers for gap detection
