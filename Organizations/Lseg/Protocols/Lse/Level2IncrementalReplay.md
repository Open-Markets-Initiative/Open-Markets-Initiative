## Lse Level2Incremental Replay: Level 2 Incremental Replay

Replay service for the London Stock Exchange Level 2 Incremental market data gateway, carrying add, modify and delete instructions over a Tcp session using Group Ticker Plant framing.

### Overview

Level 2 Incremental Replay is the retransmission service provided by the Lseg Group Ticker Plant Level 2 Incremental market data gateway for London Stock Exchange. Each gateway includes its own replay service caching the most recent application messages published on that gateway's real time channel, so a replay session returns add, modify and delete instructions rather than the full cross service line message library.

A client logs in with a Login Request, submits a Replay Request naming the first sequence number and the number of messages required, and receives the cached messages in their original order. A Replay Response reports acceptance or an explanatory status code, and a Replay and Recovery Complete message marks the end of the retransmission.

### Transport

Tcp unicast session to the Level 2 Incremental market data gateway, using the Lseg Group Ticker Plant unit header framing.

### Key Characteristics

- **Per service line** - Served by the Level 2 Incremental market data gateway, so only Level 2 Incremental messages are carried
- **Rolling cache** - Replays recent application messages by sequence number range
- **Session administration** - Login, replay request and completion messages bracket each retransmission

