## Cboe Cfe Futures Crypto Feed

Pitch feed providing market data for cryptocurrency futures contracts traded on Cboe Futures Exchange.

### Overview

Futures Crypto Feed delivers real-time market data for crypto-related futures contracts on Cboe Futures Exchange. The feed provides order book updates, trade executions, and instrument status for digital asset derivative products listed on the exchange.

The feed serves participants trading or monitoring Cboe's cryptocurrency futures offerings. It uses the Pitch protocol with message types adapted for crypto futures contract specifications and trading characteristics.

### Transport

Udp multicast with sequenced delivery and spin server gap recovery.

### Key Characteristics

- **Crypto futures data** - Market data for cryptocurrency derivative contracts
- **Order book updates** - Real-time book changes for crypto futures instruments
- **Trade executions** - Execution reports for matched crypto futures orders
- **Pitch protocol** - Standard Pitch message encoding for crypto-specific instruments
