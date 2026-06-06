## ElectronX Market Data: ElectronX NLS Fix Market Data

Fix-based market data protocol delivering Market-by-Order depth, trades, and instrument reference data for Bounded Futures and Binary Options on the ElectronX exchange.

### Overview

MarketData is delivered via a dedicated second FIX gateway separate from the order entry session. Subscribers issue a MarketDataRequest [V] for one or more symbols and receive a MarketDataSnapshotFullRefresh [W] followed by ongoing MarketDataIncrementalRefresh [X] updates when SubscriptionRequestType is Snapshot Plus Updates.

The book is presented Market-by-Order, with each order carrying an MDEntryID that matches the OrderID on the order-entry gateway so participants can identify their own orders within market data. Depth is configurable from top-of-book up to 25 levels. Instrument reference data is retrievable via SecurityListRequest [x] / SecurityList [y].

### Transport

Tcp Fix 5.0 SP2 session on the market data gateway.

### Key Characteristics

- **Separate gateway** - Market data sessions are not accessible via the order entry session
- **Market-by-Order book** - Each order rendered individually with timestamp for time priority
- **Configurable depth** - Top of book, full book (25 levels), or any depth in between
- **MDEntryID = OrderID** - Subscribers can locate their own orders in the public feed
- **Snapshot + incremental** - Initial MarketDataSnapshotFullRefresh followed by MarketDataIncrementalRefresh
- **Reference data on same gateway** - SecurityListRequest / SecurityList for instrument discovery
- **Trade matching to fills** - TradeID on market data matches TrdMatchID on ExecutionReport fills

