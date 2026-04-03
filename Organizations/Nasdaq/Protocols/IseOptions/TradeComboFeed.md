## IseOptions TradeComboFeed: Nasdaq Ise Options Trade Combo Feed

Itch market data feed providing execution reports for complex options strategies on the Nasdaq Ise exchange.

### Overview

TradeComboFeed delivers trade execution reports for complex multi-leg options strategies traded on Ise. The feed reports the net execution price, total size, and component leg details for each complex trade, providing post-trade transparency for strategy executions.

The feed uses Itch binary encoding and includes strategy definition reference data. Trade reports identify the executed strategy, net price, and individual leg execution details.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Complex trade reports** - Execution details for multi-leg strategy trades
- **Net and leg pricing** - Both net strategy price and individual leg details
- **Strategy definitions** - Leg components with series and ratio references
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
