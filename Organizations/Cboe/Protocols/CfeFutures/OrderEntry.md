## Cboe Cfe Futures Order Entry

Boe binary order entry protocol for submitting and managing orders on Cboe Futures Exchange.

### Overview

Futures Order Entry provides low-latency order management for trading on Cboe Futures Exchange using the Boe binary protocol family. The protocol supports new order submission, modification, cancellation, and execution reporting for futures contracts with compact binary message formats.

The protocol includes Boe3 generation enhancements with expanded message types and fields tailored to futures trading. It covers all listed futures contracts including Vix futures, with support for spread orders, mass cancellation, and risk controls.

### Transport

Tcp connections to Cboe Futures Exchange matching engine gateways with session authentication and heartbeat management.

### Key Characteristics

- **Binary encoded** - Compact fixed-format messages for minimal serialization overhead
- **Boe3 generation** - Current protocol with expanded futures-specific message types
- **Spread order support** - Multi-leg futures spread submission and management
- **Mass cancel** - Bulk cancellation by contract, session, or risk group
- **Risk controls** - Pre-trade risk checks and kill switch functionality
