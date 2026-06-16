## BxeEquities Trade Reporting: Cboe BXE Fix trade reporting

Financial Information eXchange (Fix) trade reporting facility (Trf) protocol for Cboe BXE, used by Systematic Internalisers to maintain quotes (Quote, Quote Cancel, Quote Status Report) and to report off-book trades (Trade Capture Report) with acknowledgements.

### Overview

The Cboe BXE Trf is a Fix port combining Systematic Internaliser quote maintenance and off-book trade reporting.

Participants submit Quote and Quote Cancel messages to maintain SI quotes and receive Quote Status Reports, and submit Trade Capture Reports for off-book trades, answered by Trade Capture Report Ack.

### Transport

Tcp Fix session per member with sequence tracking, heartbeats, and resend-based recovery.

### Key Characteristics

- **Fix** - Tag-value trade reporting facility port
- **SI quoting** - Quote / Quote Cancel / Quote Status Report
- **Trade reporting** - Trade Capture Report and acknowledgement
- **Session based** - Persistent authenticated Tcp Fix session

