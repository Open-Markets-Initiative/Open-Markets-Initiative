## SmallFutures Drop Copy: Small Exchange Drop Copy Fix Api

Financial Information eXchange encoding of the Small Exchange drop copy service, a listen only Fix session that mirrors the execution reports of the order entry session and reports trades that are later cancelled or corrected.

### Overview

The drop copy session is listen only: it carries execution reports and nothing else, so a participant reconciling its order state does not consume capacity on the order entry connection.

It carries one report the order entry session does not: the trade cancel and correct report, sent when the exchange busts or amends a trade after the fact. It uses the Small Exchange user defined MsgType UCC.

### Transport

Tcp for reliable ordered delivery over a persistent Fix session with logon, heartbeat and sequence based recovery.

### Key Characteristics

- **Listen only** - Execution reports and session messages, with no order entry
- **Trade cancel and correct** - Reports a trade busted or amended after the fact
- **User defined message** - Trade cancel and correct uses MsgType UCC

