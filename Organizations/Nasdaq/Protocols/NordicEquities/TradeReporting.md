## NordicEquities Trade Reporting: Nasdaq Nordic Fix On-Exchange Trade Reporting

Fix trade reporting protocol for manual on exchange trades on the Nasdaq Nordic equities markets running on the Inet Nordic platform.

### Overview

Members report negotiated on exchange trades as Fix 5.0 SP2 Trade Capture Reports, either one party for matching against the contra's report or two party pre locked in. The venue answers each report with a Trade Capture Report Ack and relays alleged trades, trade confirmations, trade breaks and cancel notifications as Trade Capture Reports.

Reports carry the Nordic trade type, clearing instruction, sides with executing, contra and clearing parties, and the MiFid II MMT flags for trade category, price formation, deferral and delayed dissemination.

### Transport

Tcp session framed by the Nasdaq Nordic Fixt 1.1 transport layer on a trade reporting connection separate from order entry, with sequence number recovery through Resend Request and Sequence Reset.

### Key Characteristics

- **Trade reporting** - One party for matching or two party locked in reports
- **Fix 5.0 SP2** - Trade Capture Report and acknowledgement over a Fixt 1.1 session
- **MiFid II** - MMT trade flags and post trade deferral
- **Session based** - Persistent authenticated Tcp Fix session

