## NtxEquities Match View: Nasdaq Texas View Of Away Market Best Bid And Offer

Market data feed publishing the prevailing best bid and offer of the other exchanges as the Nasdaq Texas execution system sees it, used with Ouch to prevent trade-throughs and quote-throughs.

### Overview

MatchView, formerly the Ouch Pricing Feed, is a real-time Nasdaq Texas market data feed giving the view the Nasdaq Texas execution system has of the prevailing best bid and offer of the other exchanges. It works in conjunction with Ouch and is used to prevent trade-throughs and quote-throughs.

The feed carries one ascii message line per update: a millisecond timestamp, the message type U, the stock symbol and the bid and ask prices with four implied decimal places.

### Transport

Udp multicast, single channel broadcast of timestamped ascii message lines.

### Key Characteristics

- **Away market best bid and offer** - Prevailing quotes of the other exchanges as Nasdaq Texas sees them
- **Ascii** - Fixed width ascii message lines
- **Single message** - One quote update message type

