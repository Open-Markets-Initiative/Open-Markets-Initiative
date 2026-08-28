## JnxBonds Drop Copy: Japannext Fix Drop Copy Specification Bonds

Financial Information eXchange encoding of the Japannext drop copy service for bonds, a listen only Fix session that mirrors the execution reports of the trading session so a participant can reconcile its order state without consuming the order entry connection.

### Overview

The drop copy session is listen only: it carries execution reports and nothing else, so a participant reconciling its order state does not consume capacity on the order entry connection.

Reports for orders entered over Ouch appear on the Fix drop copy as well, which is what makes it a complete record of the participant's activity rather than a mirror of one session.

### Transport

Tcp for reliable ordered delivery over a persistent Fix session with logon, heartbeat and sequence based recovery.

### Key Characteristics

- **Listen only** - Execution reports and session messages, with no order entry
- **Copy indicator** - Each report is marked as a copy of one delivered on the trading session
- **Contra broker reporting** - The firm on the other side is named on each fill

