## MiaxOptions Clearing Trade Drop: MIAX Options Clearing Trade Drop (CTD)

Messaging interface that provides real-time clearing trade information to the parties of a trade, and to entitled designated recipients, on the MIAX Options options exchange.

### Overview

MIAX Options Clearing Trade Drop (CTD) sends trades, trade corrections and trade cancels to the parties of a trade and to entitled designated recipients, with entitlements by OCC Number, CMTA and clearing member MPID. The CTD gateway collects the trades from each MIAX trading engine and provides a consolidated flow of trades to its recipients.

Trade messages carry option legs and, for complex stock-tied orders, stock legs. Besides the trade itself they give additional billing parameters, market and strategy state, the liquidity, timer and auction roles of this side, and this side's and the contra side's clearing information. Underlying symbols for stock legs can be configured per CTD port to arrive in stock ticker format rather than the OCC Options Underlying symbol format.

The System State message reports the end of application messages and the start and end of test sessions. Firms using Risk Protection Monitoring receive Risk Notification messages on their CTD session; each notification type can be configured to be forwarded or dropped, solicited notifications are sequenced and recoverable, and the unsolicited period status notification is unsequenced.

### Transport

Tcp using the MIAX proprietary SesM session management protocol for guaranteed delivery of CTD sourced messages, with a primary and a secondary port connection per recipient.

### Key Characteristics

- **Clearing trades** - Trades, trade corrections and trade cancels as they clear
- **Both sides** - This side and contra side clearing information
- **Entitlements** - By OCC Number, CMTA and clearing member MPID
- **Risk notifications** - Risk Protection Monitor events on the same session
- **SesM session** - Authentication, sequencing, heartbeats and gap fill
- **Tcp delivered** - Primary and secondary connections per recipient

