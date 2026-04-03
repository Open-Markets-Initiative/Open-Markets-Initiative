## ATP: Aquis Trading Protocol

Proprietary binary order entry protocol developed by Aquis Exchange for high-performance order management on Aquis Exchange venues.

### Overview

The Aquis Trading Protocol (ATP) is a binary order entry protocol designed for efficient low-latency interaction with the Aquis Exchange matching engine. ATP provides fixed-length messages with binary field data directly aligned to the internal message structure used by the trading system, minimizing encoding overhead and processing time.

ATP is offered alongside the industry standard FIX protocol as an order entry option for Aquis Exchange members. The protocol is used across Aquis Exchange UK, Aquis Exchange EU, and A2X Markets in South Africa which licenses the Aquis Technologies exchange platform. AsiaNext, the digital asset exchange, also uses an adaptation of the ATP specification.

Session messages such as login, logout, and heartbeat are not sequenced. Only business messages relating to orders and trades are sequenced and recoverable, keeping the session management overhead minimal while ensuring reliability for critical trading messages.

### Transport

ATP operates over TCP providing reliable ordered delivery between the trading participant and the exchange matching engine. All messages use 1-byte packing with little-endian integer representation. The protocol supports session management through login, logout, and heartbeat messages with business message sequencing and recovery for order and trade messages.

### Key Characteristics

- **Binary encoding** - Fixed-length messages with binary fields and little-endian byte ordering
- **Low latency** - Message structure aligned directly to the matching engine internal format
- **Sequenced business messages** - Order and trade messages carry sequence numbers for gap recovery
- **Lightweight session layer** - Unsequenced session management messages reduce overhead
- **Post-only support** - Supports passive order types including post-only orders
- **1-byte packing** - Compact message layout with no padding between fields
