## Memoir Depth: Memx Full Depth of Book

Sbe-encoded market data protocol providing full depth of book information for equities and options traded on Memx.

### Overview

Memoir Depth is the Memx full depth of book market data feed delivering real-time order book updates for all price levels across equities and options instruments. The protocol uses Simple Binary Encoding (Sbe) to disseminate add, modify, delete, and execution messages that allow subscribers to maintain a complete view of the order book at every price level.

The feed provides order-level granularity enabling recipients to reconstruct the full visible book state. Memoir Depth supports both equities and options instruments on the Memx exchange, delivering updates for new orders entering the book, order modifications, cancellations, and trade executions that remove liquidity from the book.

### Transport

Udp multicast with sequenced packets. Gap detection via sequence numbers with snapshot recovery available for book state synchronization.

### Key Characteristics

- **Sbe encoded** - Fixed-position, fixed-length fields for zero-copy parsing
- **Full depth** - All price levels visible in the order book
- **Equities and options** - Covers both asset classes on Memx
- **Order-level updates** - Add, modify, delete, and execution messages
- **Multicast delivery** - Udp multicast for efficient one-to-many distribution
- **Sequence numbered** - Packets carry sequence numbers for gap detection
