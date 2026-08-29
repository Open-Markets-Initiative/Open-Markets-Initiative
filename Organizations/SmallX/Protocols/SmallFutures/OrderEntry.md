## SmallFutures Order Entry: Small Exchange Fix Order Management Api

Financial Information eXchange encoding of the Small Exchange order entry interface, used by participants to submit, amend and cancel single and multi leg futures and options on futures orders, request order status, quote in size through the mass quote interface, and receive execution reports over a Fix session.

### Overview

The Small Exchange lists deliberately small notional futures and options on futures, so a single product family covers an asset class. The order entry interface reflects that: multi leg orders carry between two and four legs with a ratio of at most five, which is enough for the spreads its products are designed around without the generality a larger futures exchange needs.

Every execution report scenario the specification separates carries MsgType 8 and is told apart by ExecType, including the triggered stop report that has no equivalent on a venue without stop orders. Self match prevention is carried on the order rather than configured on the session, so a firm can decide per order which side yields.

### Transport

Tcp for reliable ordered delivery over a persistent Fix session with logon, heartbeat and sequence based recovery.

### Key Characteristics

- **Futures order entry** - Single and multi leg futures and options on futures
- **Multi leg spreads** - Two to four legs with a ratio of at most five
- **Mass quoting** - Quote in size across a set of instruments in one message
- **Self match prevention** - Carried per order, choosing which side yields
- **Manual order indicator** - Whether the order was entered by hand or by an automated system

