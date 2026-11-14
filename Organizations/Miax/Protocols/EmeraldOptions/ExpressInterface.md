## EmeraldOptions Express Interface: Miax Emerald Options MIAX Express Interface (MEI) for Market Maker quoting

Binary quoting interface Market Makers use to submit bulk quotes, enhanced quotes and complex enhanced quotes on the Miax Emerald Options exchange and receive their responses and notifications.

### Overview

The Miax Emerald Options MIAX Express Interface (MEI) is the messaging interface members approved as Market Makers use to submit quotes in the products of the underlying instruments to which they are assigned. It supports simple bulk quotes of up to 50 single sided quotes, enhanced quotes (eQuotes) carrying a single instruction, and complex eQuotes for complex strategies.

The protocol runs over Tcp with MIAX TCP Session Management (SesM) providing authentication, sequencing, heartbeats and gap fills. Administrative messages carry the series list and ARM settings, and notifications report system and trading status, protection triggers, cancels and executions.

### Transport

Tcp for authenticated MEI sessions over the SesM session layer, carrying quote, eQuote, mass cancel and protection messages and the exchange's responses and notifications.

### Key Characteristics

- **Market Maker quoting** - Bulk quotes, eQuotes and complex eQuotes
- **Risk protection** - ARM and liquidity protection settings and resets
- **SesM session** - Session layer for authentication and sequence recovery
- **Tcp delivered** - Persistent authenticated session per port

