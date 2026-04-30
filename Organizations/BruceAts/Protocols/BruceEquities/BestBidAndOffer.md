## BruceEquities Best Bid And Offer: Bruce Ats Best Bid And Offer Data

Direct data feed providing best bid and best offer quotations for securities traded on The Bruce Ats equities platform.

### Overview

Bruce Best Bid And Offer (Bbbo) is a direct market data feed product offered by The Bruce Ats, providing the platform's best bid and best offer position for every security traded. The feed is lightweight and focused: it does not carry full depth of book, instead delivering compact quotation updates suitable for subscribers who only need top of book.

Messages are delivered as a sequenced Itch-style message stream over MoldUdp64 multicast. Instruments are identified by a stock locate code - a small integer assigned dynamically each day and communicated via the Stock Directory message at session start. The feed also carries system events, stock trading actions, and Reg SHO short sale price test restricted indicators for the listed universe.

### Transport

Udp multicast via MoldUdp64 for real-time delivery of sequenced Itch-style best bid and offer messages with packet-level sequencing for gap detection.

### Key Characteristics

- **Best bid and offer** - Top of book quotations for every Bruce-traded security
- **MoldUdp64** - Packaged over the Nasdaq MoldUdp64 multicast framing
- **Itch encoded** - Fixed-width Itch-style binary messages for low latency processing
- **Stock locate codes** - Dynamic integer identifiers assigned each day via Stock Directory
- **Trading actions** - Per-instrument trading status notifications
- **Reg SHO** - Short sale price test restricted indicator updates
- **Lightweight** - Top of book only, no full depth for efficient bandwidth use

