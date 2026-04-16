## CfeFutures Crypto Feed: Cfe Bitcoin And Ether Futures Market Data

Dedicated market data feed publishing order book, trade, and reference data for Bitcoin and Ether futures traded on the Cboe Futures Exchange.

### Overview

CryptoFeed is the dedicated market data product for Bitcoin and Ether futures listed on the Cboe Futures Exchange (Cfe). It publishes order book, trade, and reference data events for the crypto futures product family on a separate feed channel so that subscribers interested only in crypto derivatives can consume the data without receiving unrelated Cfe products.

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of crypto futures quote and trade events with A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover missed multicast messages.

### Key Characteristics

- **Crypto futures** - Bitcoin and Ether futures on Cboe Cfe
- **Cboe Pitch** - Native Cboe binary message format
- **Multicast delivery** - Udp multicast with A and B feed redundancy
- **Trade reports** - Last sale messages alongside book updates
- **Gap request proxy** - Tcp recovery service for missed multicast messages

