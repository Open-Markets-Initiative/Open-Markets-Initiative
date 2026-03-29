## Memoir Last Sale: Memx Trade Feed

Sbe-encoded market data protocol providing real-time trade reports for equities traded on Memx.

### Overview

Memoir Last Sale is the Memx trade reporting feed delivering real-time last sale information for equity instruments. The protocol uses Simple Binary Encoding (Sbe) to disseminate executed trade details including price, size, trade conditions, and timestamps for all transactions occurring on the Memx equities market.

The feed provides a dedicated stream of trade execution data separate from the order book feeds, enabling subscribers to monitor trading activity, calculate volume-weighted prices, and track market statistics without processing order book updates. Memoir Last Sale includes trade correction and cancellation messages for maintaining accurate trade records.

### Transport

Udp multicast with sequenced packets. Gap detection via sequence numbers for ensuring complete trade record delivery.

### Key Characteristics

- **Sbe encoded** - Fixed-position, fixed-length fields for zero-copy parsing
- **Equities trade feed** - Last sale reports for Memx equity instruments
- **Trade conditions** - Sale condition indicators for each execution
- **Trade corrections** - Correction and cancellation messages for trade adjustments
- **Multicast delivery** - Udp multicast for efficient one-to-many distribution
- **Sequence numbered** - Packets carry sequence numbers for gap detection
