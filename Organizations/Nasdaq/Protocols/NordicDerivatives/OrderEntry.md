## NordicDerivatives Order Entry: Nasdaq Nordic Genium INET FIX

Financial Information eXchange (Fixt 1.1 session with Fix 5.0 SP2 application messages) interface to the Nasdaq Nordic Genium INET derivatives, fixed income, currency and commodities trading system, carrying order entry, linked order lists, combination and repo instrument registration, mass quotes, requests for quote, one-sided auctions, trade reporting, trade confirmations, rectify and give-ups.

### Overview

The session conforms to Fixt 1.1 with Fix 5.0 SP2 application messages. Every inbound business message names an authenticated user in SenderSubID, and further users can be authenticated on the same session with User Request. Sequence numbers reset each morning and a session lives for one trading day.

Nasdaq extends the standard where Genium INET needs it: messages taken from later Fix versions, custom tags from 20001, and custom enumerations such as the Good till End of Session time in force. Drop copy sessions mirror execution reports and trade capture reports with CopyMsgIndicator set.

### Transport

Fixt 1.1 session over Tcp to a primary and a secondary gateway, with session state replicated between them so a client can reconnect to either and recover by standard Fix resend.

### Key Characteristics

- **Order entry** - Single orders, linked order lists and mass quotes with full execution reporting
- **Trade reporting** - One and two party trade reports, OTC reports, confirmations, rectify and give ups
- **Genium INET extensions** - Nasdaq custom tags from 20001 alongside Fix 5.0 SP2
- **Fixt 1.1 session** - Primary and secondary gateways with full message recovery

