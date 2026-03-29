## OrdersApi: Coinbase Order Entry

Binary order entry protocol for submitting and managing orders on Coinbase exchange using Sbe encoding.

### Overview

OrdersApi is Coinbase's binary order entry interface providing low-latency order management for digital asset trading. The protocol supports new order submission, order cancellation, and order modification using Sbe-encoded messages designed for minimal serialization overhead and deterministic field positioning.

The protocol handles the full order lifecycle including limit orders, market orders, stop orders, and cancel requests. Execution reports provide real-time feedback on order state transitions including acknowledgments, partial fills, complete fills, and rejections. The Sbe encoding ensures consistent message sizes and fixed field offsets for efficient encoding and decoding in latency-sensitive trading systems.

### Transport

Tcp connections to Coinbase order entry gateways. Session establishment and authentication are managed by the companion Session protocol. Bidirectional message sequencing supports reliable delivery and recovery.

### Key Characteristics

- **Sbe encoded** - Fixed-position binary fields for deterministic low-latency serialization
- **Full order lifecycle** - New orders, modifications, cancellations, and execution reports
- **Multiple order types** - Limit, market, stop, and other order types for digital assets
- **Execution reports** - Real-time order state transitions and fill notifications
- **Self-trade prevention** - Controls to prevent matching against own resting orders
- **Digital asset trading** - Order management for cryptocurrency trading pairs on Coinbase
