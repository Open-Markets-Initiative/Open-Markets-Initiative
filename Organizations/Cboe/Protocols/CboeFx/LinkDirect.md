## LinkDirect: Cboe Fx LinkDirect Market Data

Itch-based market data feed providing streaming Fx quotes from liquidity providers on Cboe Fx LinkDirect.

### Overview

Fx LinkDirect delivers real-time streaming indicative and executable foreign exchange quotes from liquidity providers on the Cboe Fx LinkDirect platform. The feed provides participants with Fx pricing sourced directly from dealer liquidity rather than a central limit order book.

The feed uses Itch binary encoding conventions adapted for foreign exchange with Fx-specific message types for currency pair identification and price representation. It serves participants who access Fx liquidity through the LinkDirect dealer-to-client model rather than the Ecn order book.

### Transport

Tcp-based data feed with sequenced message delivery, session login, and heartbeat management.

### Key Characteristics

- **Dealer liquidity** - Streaming quotes from Fx liquidity providers
- **Itch-based encoding** - Binary message format following Itch conventions for Fx
- **Indicative and executable** - Both indicative and firm executable pricing available
- **LinkDirect platform** - Dealer-to-client Fx pricing model separate from the Ecn
