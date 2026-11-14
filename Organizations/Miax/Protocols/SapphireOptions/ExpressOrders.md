## SapphireOptions Express Orders: MIAX Sapphire Options Express Orders (MEO)

Binary order entry interface that MIAX Sapphire members use to submit simple bulk orders and complex binary orders for trading on the Sapphire Options Market.

### Overview

MIAX Express Orders (MEO) is the binary order entry interface for the Sapphire Options Market. It uses binary numeric fields, fixed length ASCII fields and variable length bulk messages, and refers to options by Sapphire assigned Product IDs rather than full canonical symbols and to complex strategies by Strategy IDs. Order and cancel acknowledgements come directly from the Matching Engine of the cloud that trades the underlying.

A Simple Bulk Liquidity Message carries up to 25 single-side AutoReplace Orders, Standard Binary Orders, Standard Binary Order Replaces or Standard Binary Order Cancels, processed in the order they appear, and is answered with one response that gives each order's status, engine sequence number, engine transaction time and open size. A Complex Binary Order Request sends an immediate or cancel order for a complex strategy against the complex order book. Mass cancel, selective liquidity auto purge (SLAP), protection reset, ARM and ARM2 settings and series assignment requests complete the input messages.

Notifications report the system state, underlying trading status, opening width relief, ARM and ARM2 settings and protection events, liquidity, SLAP and single side protection triggers, cancels, executions, complex strategy definitions and stock leg executions. Time fields are in United States Eastern time: NanoTime counts nanoseconds since midnight, and the firm's send time is a TimeStamp in nanoseconds since the epoch.

### Transport

Tcp using the MIAX proprietary SesM session management protocol for authentication, sequencing of messages, heartbeats and gap fills; messages of no value after a reconnect are sent unsequenced.

### Key Characteristics

- **Bulk orders** - Up to 25 orders, cancels or replaces in one message
- **Complex orders** - Immediate or cancel complex binary orders by Strategy ID
- **Risk protections** - ARM, ARM2, SLAP and single side liquidity protection
- **Product IDs** - Series referenced by session assigned Product IDs
- **SesM session** - Authentication, sequencing, heartbeats and gap fill
- **Tcp delivered** - Guaranteed delivery of order packets

