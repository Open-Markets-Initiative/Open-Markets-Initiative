## OrderService: Currenex Order Entry

Binary order entry protocol for submitting and managing Fx orders on Currenex platforms using Cbp with Ouch-based encoding.

### Overview

OrderService is Currenex's order entry protocol providing low-latency order management for foreign exchange trading. The protocol is built on the Currenex Binary Protocol (Cbp) framework using an Ouch-based message encoding, enabling efficient binary order submission, modification, cancellation, and execution reporting for Fx instruments.

The protocol supports the full Fx order lifecycle including limit orders, market orders, and streaming price acceptance. Execution reports provide real-time order state updates including acknowledgments, fills, partial fills, and rejections. The Ouch-based encoding provides a compact binary format familiar to participants using Ouch-family order entry protocols from other venues, adapted with Fx-specific fields for currency pair identification, settlement dates, and rate precision.

### Transport

Tcp connections to Currenex order entry gateways. Session establishment includes authentication, and connections are maintained through heartbeat exchanges. Bidirectional sequencing supports message recovery after reconnection.

### Key Characteristics

- **Cbp/Ouch-based encoding** - Binary message format built on Currenex Binary Protocol with Ouch conventions
- **Fx order management** - Full order lifecycle for foreign exchange instruments
- **Multiple order types** - Limit, market, and streaming price acceptance orders
- **Execution reports** - Real-time order state transitions and fill notifications
- **Fx-specific fields** - Currency pair identification, settlement dates, and rate precision
- **Low-latency binary** - Compact encoding optimized for minimal serialization overhead
