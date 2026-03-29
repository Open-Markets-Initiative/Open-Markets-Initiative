## Cboe Europe Order Entry

Boe binary order entry protocol for submitting and managing orders on Cboe European equity venues.

### Overview

Europe Order Entry provides low-latency order management for trading on Cboe Europe's regulated market and multilateral trading facilities using the Boe binary protocol. The protocol supports new order submission, modification, cancellation, and execution reporting for European equities, Etfs, and exchange-traded products.

The protocol covers all order types and time-in-force options available on Cboe European venues. It includes mass cancellation, risk controls, and session management tailored to European market structure and trading requirements.

### Transport

Tcp connections to Cboe Europe matching engine gateways with session authentication and heartbeat management.

### Key Characteristics

- **Binary encoded** - Compact fixed-format messages for minimal serialization overhead
- **European venue support** - Order entry for Cboe Europe regulated market and Mtf venues
- **Mass cancel** - Bulk cancellation by instrument, session, or risk group
- **Risk controls** - Pre-trade risk checks and kill switch functionality
