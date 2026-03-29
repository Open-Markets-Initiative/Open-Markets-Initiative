## Cboe Europe Last Sale

Apf feed providing real-time trade execution data for Cboe European equity venues.

### Overview

Europe Last Sale delivers post-trade information for all executions on Cboe Europe's regulated market and multilateral trading facilities using the Apf protocol. The feed reports trade prices, quantities, timestamps, and condition codes as matches occur across European venues.

The feed provides a trade-only data stream for consumers who need European execution data without order book depth or quote information. It covers equities, exchange-traded funds, exchange-traded products, and other instruments traded on Cboe Europe.

### Transport

Udp multicast delivery organized by instrument segment with sequence numbers for gap detection.

### Key Characteristics

- **Trade-only stream** - Execution data without order book overhead
- **Apf protocol** - Cboe Europe's dedicated last sale data format
- **European venue coverage** - Trades from Cboe Europe regulated market and Mtf venues
- **Trade conditions** - Condition codes indicating trade type and reporting context
