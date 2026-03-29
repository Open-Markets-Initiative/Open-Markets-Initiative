## Now: Currenex Market Data

Binary market data protocol for disseminating Fx market data from Currenex platforms using Cbp encoding.

### Overview

Now is Currenex's market data protocol providing real-time foreign exchange pricing and order book data using the Currenex Binary Protocol (Cbp). The protocol delivers market data including order book updates, trade reports, and instrument reference data for Fx instruments available on the Currenex trading platform.

Now serves as the core market data distribution mechanism for Currenex's electronic Fx trading venues, providing participants with the pricing information needed for trading decisions. The Cbp encoding framework offers efficient binary serialization with fixed message formats designed for high-throughput, low-latency Fx market data consumption.

### Transport

Tcp connections to Currenex market data gateways. Session management handles authentication, heartbeat monitoring, and sequence tracking for reliable message delivery.

### Key Characteristics

- **Cbp encoded** - Currenex Binary Protocol for efficient binary message serialization
- **Fx market data** - Real-time pricing and book data for foreign exchange instruments
- **Order book updates** - Book depth changes reflecting Fx liquidity and pricing
- **Trade reporting** - Executed transaction data for Fx currency pairs
- **Instrument reference data** - Currency pair definitions and trading parameters
- **Sequenced delivery** - Message sequence numbers for gap detection and recovery
