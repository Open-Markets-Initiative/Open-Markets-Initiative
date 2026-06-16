## CxaEquities Order Entry: Cboe Australia Fix order entry

Financial Information eXchange (Fix 4.2) order entry protocol for submitting, modifying, and cancelling orders on Cboe Australia equities, including the order port new order, cancel, cancel/replace, execution report, and cancel reject messages.

### Overview

Order Entry is the Fix 4.2 order port for Cboe Australia, providing members a tag-value interface to submit, modify, and cancel orders and receive execution reports. Sessions use the standard Fix session layer with Logon, Heartbeat, Test Request, Resend Request, Sequence Reset, and Logout.

The protocol covers the full order lifecycle — new order single, order cancel request, order cancel/replace request, execution report, cancel reject, and trade cancel/correct — and supports Cboe Australia order types such as Iceberg, Market on Close, Peg, BestX, MarketX, and Post-Only.

### Transport

Tcp Fix session per member with sequence tracking, heartbeats, and resend-based recovery.

### Key Characteristics

- **Fix 4.2** - Tag-value Financial Information eXchange order entry
- **Full order lifecycle** - New, cancel, cancel/replace, execution report, cancel reject
- **Session based** - Persistent authenticated Tcp Fix session per member
- **Sequence recovery** - Resend Request / Sequence Reset gap recovery

