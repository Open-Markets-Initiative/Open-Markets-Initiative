## TaifexDerivatives Market Data: Taifex Market Data Transmission Manual

Market data feed of the Taiwan Futures Exchange, multicast over the market data transmission network in the original product symbol format that the exchange names its P1 group. Carries product and contract basic data, price limits, matched prices and quantities, intra-day highs and lows, calculated and actual opening prices, sums of order data, the order book and the reference best five bid and ask, closing market data with and without settlement prices and open interest, combination product and negotiated block trade data, underlying index and foreign exchange data, indices compiled by the exchange and its partners, quote requests, contract adjustments, bulletins and system messages, together with a heartbeat.

### Overview

The exchange publishes the same market data in several product symbol formats, each its own feed on its own channels. This protocol is the P1 group, which the manual calls the original format. The P2 group carries the same content with symbols linked to the Taiwan Stock Exchange stock identifier and is published as a separate manual and separate channels, and the real-time and FLEX feeds are separate again.

A channel carries a stated subset of the message formats rather than all of them. Appendix 2 of the manual prints the matrix of channel against format, and the subsets differ between the regular and the after-hours session: the after-hours session publishes seven channels rather than ten and omits the closing market data messages that carry settlement prices, because there is no settlement process after the after-hours session closes.

Several channels require a separate application. The manual marks the underlying index, foreign exchange and compiled index channels as needing an application to receive, so a subscriber of the normal trading channels does not automatically receive them.

### Transport

Multicast over the market data transmission network, ten channels in the regular trading session and seven in the after-hours session, each channel a group and port carrying a stated subset of the message formats, published from the Banqiao primary and Taichung backup server rooms and from two source hosts per market in each.

### Key Characteristics

- **Original symbol format** - The P1 group feed, whose product symbols are the exchange's own rather than linked to a stock identifier
- **Channel scoped** - Ten regular and seven after-hours channels, each carrying a stated subset of the message formats
- **Dual sourced and dual sited** - Each market is published from two source hosts in each of the Banqiao and Taichung server rooms
- **Separate block trade channels** - Block trade data, including combination product and negotiated block trades, is carried on channels of its own
- **Application gated channels** - The underlying index, foreign exchange and compiled index channels require a separate application to receive

