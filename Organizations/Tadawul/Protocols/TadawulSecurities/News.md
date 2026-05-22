## TadawulSecurities News: Saudi Exchange X-stream Itch News Dissemination

Itch news feed disseminating exchange news items including title, reference, and news text in Arabic or English alongside reference data and trading status events for Saudi Exchange listed securities.

### Overview

News is the exchange news feed for the Saudi Exchange. It publishes News items linked to specific orderbooks or to the system as a whole, with each item carrying a title, a reference URL or pathname, and the full news text in Arabic or English.

The feed also carries reference data push messages and trading status changes so that subscribers can correlate news items with the affected instruments and their current trading state.

### Transport

Point-to-point delivery via SoupBinTcp for client connections to the News feed.

### Key Characteristics

- **News dissemination** - News items with title, reference, and news text published by the exchange
- **Bilingual content** - News items carry a language code distinguishing Arabic and English text
- **Variable length text** - Title, reference, and news text are null-terminated alpha fields with maximum lengths defined in the message specification
- **X-stream platform** - Nasdaq X-stream matching engine licensed and operated by the Saudi Exchange
- **Trading status** - Orderbook trading action messages disseminate suspension and unsuspension events alongside the news content
- **Itch encoded** - Compact fixed-width Itch-style binary messages for low latency processing

