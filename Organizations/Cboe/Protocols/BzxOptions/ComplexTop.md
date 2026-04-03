## Cboe Bzx Options Complex Top Of Book

Pitch feed providing best bid and offer updates for complex multi-leg options strategies on Cboe Bzx Options Exchange.

### Overview

Options Complex Top Of Book delivers lightweight real-time best bid and offer data for complex options strategies traded on Cboe Bzx Options Exchange. The feed provides top-of-book quotes for multi-leg instruments without the overhead of full complex depth.

The feed serves participants who need best price visibility for complex strategies but do not require individual order tracking. It includes strategy definitions, top-of-book updates, and execution data for complex instruments.

### Transport

Udp multicast with sequenced delivery and spin server gap recovery.

### Key Characteristics

- **Complex Bbo** - Best bid and offer for multi-leg options strategies
- **Low bandwidth** - Compact messages without full complex depth overhead
- **Strategy definitions** - Component leg and ratio information for each instrument
- **Execution data** - Trade reports for complex strategy matches
