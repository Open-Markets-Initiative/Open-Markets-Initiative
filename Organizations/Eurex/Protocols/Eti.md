## Eti: Enhanced Trading Interface

Binary order entry protocol for submitting and managing orders on the Eurex T7 trading platform for derivatives and cash equity instruments.

### Overview

Eti (Enhanced Trading Interface) is Deutsche Boerse's high-performance order entry protocol for the T7 trading platform, providing direct electronic access to Eurex derivatives and Xetra/Boerse Frankfurt cash equity markets. The protocol supports order submission, modification, cancellation, mass operations, and market maker quoting through a binary message format optimized for low-latency trading.

Eti handles the full spectrum of T7 order management including standard orders, stop orders, trailing stops, iceberg orders, and complex instrument orders. Market makers use dedicated quote entry and mass quote messages for efficient two-sided pricing. The protocol supports pre-trade risk controls including transaction limits, maximum order quantity checks, and kill switch functionality. Session management provides authentication, throttling, and persistent order association across reconnections.

### Transport

Tcp connections to T7 trading gateways. Sessions are established with user authentication and session identifiers. Heartbeat monitoring maintains connection liveness. Message throttling enforces fair access and risk limits at the session level.

### Key Characteristics

- **Binary encoded** - Compact fixed-format messages for low-latency order management
- **T7 platform** - Order entry for Eurex derivatives and cash equity matching engines
- **Market maker quoting** - Dedicated mass quote functionality for two-sided pricing
- **Pre-trade risk controls** - Transaction limits, quantity checks, and kill switch
- **Complex instruments** - Order entry for multi-leg strategies and user-defined instruments
- **Session persistence** - Orders persist across session reconnections by default
- **Mass operations** - Bulk cancellation by instrument, session, or user group
