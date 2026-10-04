## Tsx Global Fx: Tmx Global Fx reference price feed

Reference price feed reporting bid and offer foreign exchange spot prices at each of several pre-configured size tiers for a currency pair.

### Overview

Tmx Global Fx is a reference price feed for foreign exchange spot. Each datagram names a currency pair and reports a bid and an offer price at every pre-configured size tier, so a subscriber sees the price available at each size rather than a single top of book. Tiers with no liquidity are still sent, marked with a status of Z.

Prices are a signed mantissa with an exponent field of its own, so each tier states its own precision. Price Terms says whether the tier size is in the base or the counter currency, and which way round the price is quoted. Every datagram carries a time to live, and a stream is refreshed periodically even when prices have not changed, so a subscriber can tell stale prices from quiet ones.

### Transport

Udp datagrams, one per currency pair refresh, each carrying the bid and offer reference price at every configured size tier.

### Key Characteristics

- **Foreign exchange** - Spot reference prices for currency pairs
- **Size tiered** - A bid and offer price at each pre-configured size tier
- **Single datagram** - One message type with a fixed portion and a repeating tier
- **Time to live** - Each datagram states how long its prices stay valid

