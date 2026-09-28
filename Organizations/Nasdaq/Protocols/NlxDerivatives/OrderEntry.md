## NlxDerivatives Order Entry: FIX for NLX

Financial Information eXchange (Fixt 1.1 session with Fix 5.0 SP2 application messages) interface to NLX on Genium INET, carrying order entry, tailor-made combination registration, mass quotes, requests for quote, market maker protection, two-party and multileg trade reporting and trade confirmations.

### Overview

The session conforms to Fixt 1.1 with Fix 5.0 SP2 application messages and CompIDs NLX (production) or NLX_TEST (test). Every inbound business message names an authenticated user in SenderSubID, and further users can be authenticated on the same session with User Request.

NLX extends the standard where Genium INET needs it: a custom Multileg Trade Report and market maker protection messages, custom tags from 20015 such as the clearing AccountCode, and custom enumerations such as the Holding trade report status.

### Transport

Fixt 1.1 session over Tcp to a primary and a secondary gateway, with session state replicated between them so a client can reconnect to either and recover by standard Fix resend.

### Key Characteristics

- **Order entry** - Single and combination orders and mass quotes with full execution reporting
- **Trade reporting** - Two-party and multileg trade reports and trade confirmations
- **NLX extensions** - NLX custom tags and messages alongside Fix 5.0 SP2
- **Fixt 1.1 session** - Primary and secondary gateways with full message recovery

