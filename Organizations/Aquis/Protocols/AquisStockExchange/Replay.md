## AquisStockExchange Replay: Aquis Stock Exchange market data replay

Tcp replay service of the Aquis Market Data (Amd) protocol, recovering messages missed from an Aquis Stock Exchange real time feed.

### Overview

A recipient logs in with credentials AQSE provides; the server answers with a Replay Response or drops the connection. A Replay Request is answered with the requested messages, or a Replay Response explaining the failure (section 2.3).

### Transport

A Tcp/Ip replay server for each feed: a Login message, then Replay Request messages for ranges of sequence numbers.

### Key Characteristics

- **Gap recovery** - Replays ranges of missed messages by sequence number

