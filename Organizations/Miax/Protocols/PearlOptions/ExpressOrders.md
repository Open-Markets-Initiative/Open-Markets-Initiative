## PearlOptions Express Orders: MIAX Pearl Options Express Orders (MEO)

Binary order entry interface that MIAX Pearl members use to submit bulk orders, cancels and replaces for trading on the Pearl Options Market.

### Overview

MIAX Express Orders (MEO) is the binary order entry interface for the Pearl Options Market. It uses binary numeric fields, fixed length ASCII fields and variable length bulk messages, refers to options by Pearl assigned Product IDs rather than canonical symbols, and lets Market Makers self-assign symbols to provide liquidity. Order and cancel acknowledgements come directly from the Matching Engine of the cloud that trades the underlying.

A Bulk Liquidity Message carries up to 25 single-side AutoReplace Orders, Standard Orders, Standard Order Replaces or Standard Order Cancels, processed in the order they appear, and is answered with one response that gives each order's status, engine sequence number and open size. Mass cancel, selective liquidity auto purge (SLAP), protection reset, ARM and ARM2 settings, series assignment and self-trade protection designation requests complete the input messages.

Notifications report the system state, underlying trading status, opening width relief, ARM and ARM2 settings and protection events, liquidity, SLAP and single side protection triggers, order copies, done for the day status, cancels and executions. Notifications can be enabled per port. Time fields are in United States Eastern time: NanoTime counts nanoseconds since midnight, and the firm's send time is a TimeStamp in nanoseconds since the epoch.

### Transport

Tcp using the MIAX proprietary SesM session management protocol for authentication, sequencing of messages, heartbeats and gap fills; messages of no value after a reconnect are sent unsequenced.

### Key Characteristics

- **Bulk orders** - Up to 25 orders, cancels or replaces in one message
- **Product IDs** - Series referenced by session assigned Product IDs
- **Risk protections** - ARM, ARM2, SLAP and single side liquidity protection
- **Port types** - Full service, limited service and priority mass cancel ports
- **SesM session** - Authentication, sequencing, heartbeats and gap fill
- **Tcp delivered** - Guaranteed delivery of order packets

