## PhlxOptions Drop Copy: Nasdaq PHLX FIX DROP

Financial Information eXchange (Fix) 4.2 drop copy for Nasdaq PHLX, delivering a read only copy of order and trade activity as Execution Reports.

### Overview

The FIX DROP copies the order and trade activity of a firm's order entry and quoting sessions (FIX, OTTO and SQF) onto a separate outbound Fix session. The member configures trade, order or both types of messages, selected by Account, Firm, OCC Account Number and/or CMTA, and every update arrives as an Execution Report.

Execution Reports carry the counterparty clearing firm, OCC number and capacity, manual trade, trade cancel and post trade allocation reporting, and, from version 2.1, floor broker and floor order source for Phlx floor trades. A drop host can deliver information for several firms in a service bureau configuration.

### Transport

Tcp for a persistent authenticated Fix 4.2 drop session with standard sequence-number recovery; one drop account can be bound to several parallel drop instances for fault redundancy, with one active connection at a time.

### Key Characteristics

- **Drop copy** - Read only copy of order and trade activity
- **Fix 4.2** - Execution Reports over a standard Fix 4.2 session
- **Contra side** - Counterparty clearing firm, OCC number and capacity
- **Service bureau** - One drop host can serve several authorized firms

