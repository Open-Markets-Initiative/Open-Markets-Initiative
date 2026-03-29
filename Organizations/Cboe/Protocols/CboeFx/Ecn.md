## Ecn: Cboe Fx Ecn Market Data

Itch-based market data feed providing full depth of book for spot Fx currency pairs on Cboe Fx Ecn.

### Overview

Fx Ecn delivers real-time order-by-order market data for spot foreign exchange currency pairs traded on the Cboe Fx electronic communication network. The feed shows individual order-level activity on the central limit order book, enabling subscribers to reconstruct full depth for each currency pair.

The feed uses the Itch binary encoding conventions adapted for foreign exchange, with Fx-specific message types for currency pair identification, price representation, and settlement date handling. It provides full book visibility for participants trading on the Cboe Fx Ecn venue.

### Transport

Tcp-based data feed with sequenced message delivery, session login, and heartbeat management.

### Key Characteristics

- **Order-level depth** - Individual order visibility on the Fx Ecn central limit order book
- **Itch-based encoding** - Binary message format following Itch conventions for Fx
- **Spot Fx coverage** - Currency pair data for the Cboe Fx Ecn venue
- **Sequenced delivery** - Message sequence numbers for reliable gap detection and recovery
