## JnxEquities Order Entry: Japannext Fix Trading Specification Equities

Financial Information eXchange encoding of the Japannext order entry interface for equities, used by participants to submit, amend and cancel orders on the Japannext Pts equities venue and to receive execution reports, cancel rejects and trading session status over a Fix session.

### Overview

Japannext offers order entry over both Fix and Ouch. The Fix interface is the general purpose one, carrying the fuller order and execution vocabulary, while Ouch is the lighter binary path for latency sensitive participants. Both reach the same matching engine, so a participant chooses on integration cost rather than on function.

The specification separates its execution reports by scenario — order rejected, accepted, status, canceled, replaced and trade — but all of them are MsgType 8, distinguished by ExecType and OrdStatus. Japan specific order attributes are carried in the cash and margin fields, including the user defined margin transaction type.

### Transport

Tcp for reliable ordered delivery of order entry and execution report messages over a persistent Fix session with logon, heartbeat and sequence based recovery.

### Key Characteristics

- **Equities order entry** - Order submission, amendment and cancellation for the Japannext Pts equities venue
- **Margin trading** - Cash and margin order classification, with the Japannext margin transaction type
- **Short selling** - Sell short and sell short exempt sides for Japanese short sale regulation
- **Trade prevention** - Self trade prevention reported through the execution restatement reason

