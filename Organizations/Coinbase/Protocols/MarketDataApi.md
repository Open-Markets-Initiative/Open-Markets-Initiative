## MarketDataApi: Coinbase Market Data

Binary market data protocol for receiving real-time order book and trade data from Coinbase exchange using Sbe encoding.

### Overview

MarketDataApi is Coinbase's binary market data interface providing real-time streaming of order book updates, trade executions, and instrument reference data for digital assets traded on the Coinbase exchange. The protocol uses Simple Binary Encoding (Sbe) for compact, deterministic message serialization that enables efficient low-latency consumption.

The feed delivers incremental order book updates showing changes to the full depth of book, along with trade messages reporting matched executions. Instrument definition messages provide reference data for available trading pairs including tick sizes, lot sizes, and trading status. The Sbe encoding provides fixed-position field access without sequential parsing, supporting high-throughput market data processing.

### Transport

Tcp connections to Coinbase market data gateways. Session establishment and authentication are handled by the companion Session protocol. Messages are sequenced for gap detection and ordered delivery.

### Key Characteristics

- **Sbe encoded** - Fixed-position binary fields for efficient zero-copy parsing
- **Real-time book updates** - Incremental depth of book changes for all trading pairs
- **Trade reporting** - Matched execution data with price, quantity, and aggressor side
- **Instrument definitions** - Reference data for trading pairs and instrument parameters
- **Sequenced delivery** - Message sequence numbers for gap detection
- **Digital asset coverage** - Market data for cryptocurrency trading pairs on Coinbase
