## Lse Level1: Level 1

Level 1 top of book service publishing the consolidated best bid and offer for London Stock Exchange instruments over the Group Ticker Plant.

### Overview

Level 1 is the Lseg Group Ticker Plant top of book service for London Stock Exchange. A Top of Book message is published following any change to the consolidated best bid and offer, carrying aggregated market and limit sizes for both sides together with flags indicating whether further executable depth exists below the touch.

The service also carries the System Event, Instrument Directory, Instrument Status, Order Book Clear, Trade, Statistics and Statistics Update messages, so a subscriber can maintain a complete level 1 view and the accompanying reference and statistical data from a single channel.

### Transport

Udp multicast using the Lseg Group Ticker Plant unit header framing for real time delivery of sequenced binary messages. Tcp for the Group Ticker Plant replay and recovery services used to recover missed multicast messages.

### Key Characteristics

- **Streaming top of book** - Best bid and offer updated on every change to the consolidated book
- **Depth indication** - Flags signal executable depth below the best bid and offer
- **Day statistics** - Volume, VWAP, turnover and auction statistics accompany the book

