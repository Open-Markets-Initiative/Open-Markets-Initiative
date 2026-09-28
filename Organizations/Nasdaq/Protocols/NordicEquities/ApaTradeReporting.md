## NordicEquities Apa Trade Reporting: Nasdaq Nordic Fix Off-Exchange Approved Publication Arrangement Trade Reporting

Fix trade reporting protocol for off exchange over the counter and systematic internaliser trades published through the Nasdaq Approved Publication Arrangement on the Inet Nordic platform.

### Overview

The reporting party submits two party, pre locked in Fix 5.0 SP2 Trade Capture Reports for over the counter and systematic internaliser trades, amends them with an addendum or cancels them with a trade break. The venue answers each report with a Trade Capture Report Ack and relays confirmations, corrections and breaks as Trade Capture Reports.

Reports carry the MiFid II post trade transparency fields: price type and notional amount, commodity units, MMT flags for trade category, price formation and deferral, regulatory report type, requested publication time and the credit rating used for bond deferrals.

### Transport

Tcp session framed by the Nasdaq Nordic Fixt 1.1 transport layer on a trade reporting connection shared with on exchange trade reporting, with sequence number recovery through Resend Request and Sequence Reset.

### Key Characteristics

- **Apa trade reporting** - Over the counter and systematic internaliser trades
- **Fix 5.0 SP2** - Trade Capture Report and acknowledgement over a Fixt 1.1 session
- **MiFid II** - Post trade transparency, MMT flags and deferrals
- **Session based** - Persistent authenticated Tcp Fix session

