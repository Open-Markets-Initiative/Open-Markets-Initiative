## PearlOptions Clearing Trade Drop: MIAX Pearl Options Clearing Trade Drop (CTD)

Messaging interface that provides real-time clearing trade information to the parties of a trade, and to entitled designated recipients, on the MIAX Pearl Options options exchange.

### Overview

MIAX Pearl Options Clearing Trade Drop (CTD) sends trades, trade corrections and trade cancels to the parties of a trade and to entitled designated recipients, with entitlements by OCC Number, CMTA and clearing member MPID. The CTD gateway collects the trades from each Pearl trading engine and provides a consolidated flow of trades to its recipients.

Trade messages carry option trades from FIX and binary (MEO) orders. Besides the trade itself they give additional billing parameters, the market state and free trading condition, this side's liquidity information, and this side's and the contra side's clearing information.

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

