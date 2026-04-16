## Fix: Aquis Stock Exchange Fix Market Data

Fix 4.4 market data protocol disseminating trade capture reports, quotes, market states, and participant suspension events for securities listed on the Aquis Stock Exchange.

### Overview

Aquis Fix is the market data feed of the Aquis Stock Exchange (Aqse), disseminating trade capture reports, quote updates, market state changes, security suspensions and restorations, and Fix participant suspension events using the Fix 4.4 protocol. It is the recommended interface for subscribers who prefer a standards-based tagged-value market data feed.

The feed delivers data over authenticated Fix sessions using standard market data subscription and response messages. Continuous trading data is distributed via the proprietary Amd multicast feed instead; this Fix feed focuses on trade reporting, quotes, and state transitions that benefit from reliable Tcp delivery rather than multicast dissemination.

### Transport

Tcp for authenticated Fix 4.4 sessions delivering market data subscription responses, trade capture reports, and security status updates over a persistent session.

### Key Characteristics

- **Fix 4.4** - Industry-standard tagged value protocol
- **Trade capture reports** - Detailed post-trade information with conditions and references
- **Quotes** - Real-time quotation updates for listed securities
- **Market state** - Session and instrument-level trading status transitions
- **Security suspensions** - Suspension and restoration events for individual securities
- **Participant suspensions** - Suspension and restoration events for Fix participants
- **Authenticated sessions** - Standard Fix login over Tcp

