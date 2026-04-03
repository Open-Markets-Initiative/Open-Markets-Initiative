## Cboe Edga Equities Order Entry

Boe binary order entry protocol for submitting and managing orders on Cboe Edga Equities Exchange.

### Overview

Equities Order Entry provides low-latency order management for trading on Cboe Edga Equities Exchange using the Boe binary protocol. The protocol supports new order submission, modification, cancellation, and execution reporting with compact binary message formats designed for minimal encoding overhead.

The protocol covers all order types and time-in-force options available on the Edga equity exchange. It includes mass cancellation, risk controls, and session management for robust production trading.

### Transport

Tcp connections to Cboe matching engine gateways with session authentication and heartbeat management.

### Key Characteristics

- **Binary encoded** - Compact fixed-format messages for minimal serialization overhead
- **Full order lifecycle** - New, modify, cancel, and execution reporting
- **Mass cancel** - Bulk cancellation by instrument, session, or risk group
- **Risk controls** - Built-in pre-trade risk checks and kill switch functionality
