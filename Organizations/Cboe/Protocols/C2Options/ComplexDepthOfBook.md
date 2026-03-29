## Cboe C2 Options Complex Depth Of Book

Pitch multicast feed providing order-level depth of book for complex multi-leg options strategies on Cboe C2 Options Exchange.

### Overview

Options Complex Depth Of Book delivers real-time order-by-order market data for complex options strategies traded on Cboe C2 Options Exchange. The feed shows individual order activity for user-defined and exchange-defined multi-leg strategy combinations, enabling full book reconstruction for complex instruments.

The feed includes strategy definition messages identifying the component legs, ratios, and sides of each complex instrument. Subscribers can track order and execution activity on the complex order book independently from the individual series feeds.

### Transport

Udp multicast with sequenced delivery and spin server gap recovery.

### Key Characteristics

- **Complex strategy depth** - Full order-level book for multi-leg options strategies
- **Strategy definitions** - Component leg, ratio, and side information for each complex instrument
- **Order-level detail** - Individual order add, modify, and cancel messages
- **Execution reporting** - Trade messages for complex strategy executions
