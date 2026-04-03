## Cboe Edgx Options Order Entry

Boe binary order entry protocol for submitting and managing orders on Cboe Edgx Options Exchange.

### Overview

Options Order Entry provides low-latency order management for trading on Cboe Edgx Options Exchange using the Boe binary protocol. The protocol supports new order submission, modification, cancellation, and execution reporting for individual series and complex multi-leg strategies.

The protocol includes market maker quoting functionality, mass cancellation, complex order entry, and risk controls tailored to options trading requirements.

### Transport

Tcp connections to Cboe matching engine gateways with session authentication and heartbeat management.

### Key Characteristics

- **Binary encoded** - Compact fixed-format messages for minimal serialization overhead
- **Complex order support** - Multi-leg strategy order submission and management
- **Market maker quoting** - Efficient bulk quote submission for options market makers
- **Mass cancel** - Bulk cancellation by class, session, or risk group
- **Risk controls** - Pre-trade risk checks and kill switch functionality
