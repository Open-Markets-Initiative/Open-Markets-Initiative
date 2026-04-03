## Cboe Bzx Equities Last Sale

Pitch feed providing real-time trade execution data for Cboe Bzx Equities Exchange.

### Overview

Equities Last Sale delivers post-trade information for all executions on Cboe Bzx Equities Exchange. The feed reports trade prices, quantities, timestamps, and condition codes as matches occur on the exchange matching engine.

The feed provides a trade-only data stream for consumers who need execution data without order book depth or quote information.

### Transport

Udp multicast with sequenced delivery and spin server gap recovery.

### Key Characteristics

- **Trade-only stream** - Execution data without order book overhead
- **Real-time reporting** - Trade prices and quantities as matches occur
- **Trade conditions** - Condition codes indicating trade type and context
