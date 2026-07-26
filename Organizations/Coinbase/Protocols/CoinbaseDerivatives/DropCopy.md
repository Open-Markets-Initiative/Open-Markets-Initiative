## CoinbaseDerivatives Drop Copy: Coinbase Derivatives Fix Drop Copy

Financial Information eXchange (Fix) drop copy interface for Coinbase Derivatives delivering execution reports for trades, trade busts, order status, and end of day events to risk and back office systems.

### Overview

The Coinbase Derivatives drop copy api is a Fix 4.4 session that sends Execution Report messages to the connected client to mirror order events occurring on the exchange. Customers can choose to receive messages at two levels: trade execution reports covering fills, trade busts, and trade corrections, or full order status additionally covering order placement, cancellation, replacement, rejection, done for day, and expiration events.

Each execution report carries a Parties repeating group identifying the executing firm, trader, and clearing relationships for the reported event, allowing risk and back office systems to attribute activity without a separate reference feed.

### Transport

Tcp for authenticated Fix 4.4 sessions delivering copies of execution reports with sequence-number gap recovery via Resend Request and Sequence Reset.

### Key Characteristics

- **Fix 4.4 session** - Standard Fix session layer with logon, heartbeat, and resend recovery
- **Execution report mirror** - Copies of fills, busts, corrections, and order lifecycle events
- **Two coverage levels** - Trade-only or full order status subscription
- **Party attribution** - Parties repeating group identifying firm and trader on each report

