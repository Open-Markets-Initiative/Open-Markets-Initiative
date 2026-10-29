## Mdi: Market Data Interface

Bse's netted price level market data feed, aggregating order book changes over a netting interval and publishing fewer price levels than Emdi, with only statistics and the last trade of each interval for on-exchange trades. Snapshots and incremental updates share one channel, encoded as Fix 5.0 Sp2 messages in Fast 1.2 on Ip multicast.

### Overview

Bse Mdi is a licensed deployment of the T7 Market Data Interface, designed for participants that do not need every order book update. The manual gives a netting interval of 0.47 seconds and a depth of five for benchmark products, and 0.67 seconds for the rest.

Because snapshots travel in band they may carry new information, and a Refresh Indicator in the snapshot says whether it is to be applied. Snapshots also serve as the functional beacon, so the feed sends no separate beacon message.

Every Udp datagram opens with a Fast encoded packet header and a Fast reset message that clears the global dictionary, so each datagram decodes on its own.

### Transport

Ip multicast, with snapshots and incremental updates delivered in band on the same address and port.

### Key Characteristics

- **Netted** - Order book changes aggregated over a netting interval
- **In band snapshots** - Snapshots and incremental updates share one channel
- **Lower bandwidth** - Fewer price levels and trade statistics in place of every trade
- **Self contained datagrams** - A packet header and a dictionary reset open every datagram
- **Fast 1.2** - Fix 5.0 Sp2 messages Fast encoded, with Fast 1.1 compatible templates also published

