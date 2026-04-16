## Drop Copy: Euronext Optiq Sbe Drop Copy

Sbe-encoded drop copy channel for the Euronext Optiq trading platform delivering a copy of all order entry and execution activity to back office and risk systems.

### Overview

Drop Copy is a read-only side channel of the Euronext Optiq Order Entry Gateway that mirrors order events and execution reports for a member firm, delivering them to back office, risk, and compliance systems without requiring those systems to connect to the primary order entry sessions. It provides real-time visibility into all order flow for the firm across Euronext Optiq markets.

The wire format is consistent with the Optiq order entry gateway, using Fix Simple Binary Encoding (Sbe) for fixed-width messages. Drop copy clients receive execution reports, order status updates, and cancellation confirmations but do not submit orders on the channel, which keeps the downstream systems strictly in a monitoring role.

### Transport

Tcp for authenticated drop copy sessions carrying a read-only copy of order events and execution reports for back office, risk, and compliance systems.

### Key Characteristics

- **Read-only** - Drop copy clients observe but do not submit orders
- **Sbe encoded** - Same Sbe format as the Optiq order entry gateway
- **Execution reports** - Full order lifecycle visibility for back office systems
- **Back office target** - Designed for risk, compliance, and post-trade infrastructure
- **Firm wide** - Mirrors all order activity for a member firm across Optiq markets
- **Session based** - Authenticated Tcp session with sequence tracking

