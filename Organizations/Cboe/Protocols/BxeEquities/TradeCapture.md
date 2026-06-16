## BxeEquities Trade Capture: Cboe BXE Fix trade capture

Financial Information eXchange (Fix) Trade Capture Report protocol for Cboe BXE, used to submit off-book and reported trades and to receive trade capture report acknowledgements and exchange-published trade capture reports.

### Overview

The Trade Capture Report protocol is a dedicated Fix port for submitting trade capture reports (off-book and reported trades) to Cboe BXE and receiving acknowledgements and exchange-generated trade capture reports.

Inbound participant-to-Cboe BXE Trade Capture Reports are answered with Trade Capture Report Ack, and the exchange publishes Trade Capture Reports back for matched and reported trades.

### Transport

Tcp Fix session per member with sequence tracking, heartbeats, and resend-based recovery.

### Key Characteristics

- **Fix** - Tag-value trade capture report port
- **Trade reporting** - Submit off-book and reported trades
- **Acknowledged** - Trade Capture Report Ack responses

