## NsmEquities MatchView: Nasdaq Stock Market Match View

Itch market data feed providing execution match details for Nasdaq Stock Market securities.

### Overview

MatchView delivers detailed execution match information for trades on the Nasdaq Stock Market, including match identifiers, counterparty attribution, and execution quality metrics. The feed provides post-trade transparency beyond what is available in standard last sale reporting.

The feed uses Itch binary encoding and reports execution details as matches are confirmed by the Nasdaq matching engine. MatchView is targeted at subscribers who need granular trade match data for execution analysis, best execution reporting, and post-trade analytics.

### Transport

MoldUdp64 multicast with SoupBinTcp replay.

### Key Characteristics

- **Match details** - Execution match identifiers and counterparty information
- **Post-trade data** - Detailed execution quality and attribution
- **Itch binary encoding** - Compact fixed-length fields with single-byte message types
- **Analytics focused** - Designed for execution analysis and best execution reporting
