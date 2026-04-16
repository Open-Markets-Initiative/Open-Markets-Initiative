## CboeFx Ecn: Cboe Fx Ecn Price Stream

Binary market data feed publishing executable streaming prices for spot and forward foreign exchange traded on the Cboe Fx Ecn platform.

### Overview

Cboe Fx Ecn is the electronic communication network for foreign exchange on the Cboe Fx platform. The Ecn market data feed publishes executable streaming prices from liquidity providers for spot and forward currency pairs, enabling price takers to see live tradable quotes and request execution against them.

### Transport

Tcp for authenticated Ecn subscriber sessions delivering streaming price updates over a persistent reliable connection. Udp multicast for low-latency broadcast of price updates to subscribers on controlled networks.

### Key Characteristics

- **Cboe Fx Ecn** - Electronic communication network for spot and forward Fx
- **Executable prices** - Streaming quotes that can be traded against
- **Liquidity provider sourced** - Prices supplied by market makers on the venue
- **Dual transport** - Tcp for reliability and Udp for low latency
- **Authenticated subscribers** - Credentialled access to the price stream

