## CxaEquities Trade Capture: Cboe Australia Fix trade capture report port

Financial Information eXchange (Fix 4.2) Trade Capture Report protocol for Cboe Australia, used to submit off-book and reported trades and to receive trade capture report acknowledgements and exchange-published trade capture reports.

### Overview

The Trade Capture Report protocol is a dedicated Fix port for submitting trade capture reports (off-book and reported trades) to Cboe Australia and receiving acknowledgements and exchange-generated trade capture reports.

Inbound participant-to-Cboe Trade Capture Reports are answered with Trade Capture Report Ack, and Cboe publishes Trade Capture Reports back to the participant for matched and reported trades.

### Transport

Tcp Fix trade capture session per member.

### Key Characteristics

- **Fix 4.2** - Tag-value trade capture report port
- **Trade reporting** - Submit off-book and reported trades
- **Acknowledged** - Trade Capture Report Ack responses

