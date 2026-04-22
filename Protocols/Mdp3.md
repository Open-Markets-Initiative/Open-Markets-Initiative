## Mdp3: Cme Globex Sbe Market Data

Sbe-encoded multicast market data platform publishing real-time order book, trade, and reference data for futures and options traded on Cme Globex.

MDP3 is Cme's flagship Sbe multicast market data feed covering futures and options across the Cme Globex complex including Cbot, Nymex, and Comex.

### Overview

Mdp3 is the Cme Market Data Platform version 3, the primary market data distribution channel for futures and options traded on the Cme Globex electronic trading platform. It publishes the full order book, trade events, security definitions, trading status, and settlement data for every instrument listed on the Cme complex including Cbot, Nymex, and Comex contracts.

Messages are encoded using Fix Simple Binary Encoding (Sbe) for fixed-width low-latency processing and distributed over Ip multicast with A and B channel redundancy. Complementary Tcp recovery services provide market recovery, instrument definition snapshots, and session-based snapshot recovery for subscribers that miss packets or join mid-day.

### Transport

Udp multicast for real-time delivery of sequenced Sbe market data messages over A and B feed channels with per-packet sequence numbers. Tcp for the Cme recovery services including market recovery, instrument definition, and snapshot recovery channels.

### Key Characteristics

- **Cme Globex** - Futures and options across the Cme complex
- **Sbe encoded** - Fix Simple Binary Encoding for low latency
- **Multicast delivery** - Udp multicast with A and B channel redundancy
- **Full order book** - Incremental refresh with market-by-price and market-by-order
- **Recovery services** - Market, instrument, and snapshot recovery over Tcp
- **Security definitions** - Instrument reference data integrated with the feed
- **Settlement data** - End-of-day settlement and open interest messages

