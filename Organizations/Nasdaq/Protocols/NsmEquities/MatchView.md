## NsmEquities Match View: Nasdaq View Of Away Market Best Bid And Offer

Ascii market data feed publishing the best bid and offer of the other exchanges as the Nasdaq execution system sees them, formerly known as the Ouch Pricing Feed.

### Overview

MatchView, formerly known as the Ouch Pricing Feed, is a real-time Nasdaq direct data feed that provides a view into what the Nasdaq execution system sees as the prevailing best bid and offer of the other exchanges. It may be used with Ouch order entry to help prevent trade-throughs and quote-throughs.

The feed carries a single ascii message type, "U", holding a millisecond timestamp, the stock symbol and the away best bid and ask prices. Prices are ten ascii digits, six whole and four implied decimal places, space padded on the left.

### Transport

Udp multicast, a single broadcast channel with A and B feeds, carrying timestamped ascii message lines.

### Key Characteristics

- **Away market quotes** - Best bid and offer of the other exchanges as seen by Nasdaq
- **Trade-through protection** - Companion to Ouch for trade-through and quote-through prevention
- **Single message** - One ascii "U" update message
- **Ascii Itch** - Fixed width ascii fields with a millisecond timestamp
- **Udp multicast** - Single broadcast channel with A and B feeds

