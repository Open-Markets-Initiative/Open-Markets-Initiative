## Lse Mifid2Post Trade Replay: MiFID II Post Trade Replay

Replay service for the London Stock Exchange MiFID II Post Trade market data gateway, carrying MiFID II post trade transparency reports over a Tcp session using Group Ticker Plant framing.

### Overview

MiFID II Post Trade Replay is the retransmission service provided by the Lseg Group Ticker Plant MiFID II Post Trade market data gateway for London Stock Exchange. Each gateway includes its own replay service caching the most recent application messages published on that gateway's real time channel, so a replay session returns MiFID II post trade transparency reports rather than the full cross service line message library.

A client logs in with a Login Request, submits a Replay Request naming the first sequence number and the number of messages required, and receives the cached messages in their original order. A Replay Response reports acceptance or an explanatory status code, and a Replay and Recovery Complete message marks the end of the retransmission.

### Transport

Tcp unicast session to the MiFID II Post Trade market data gateway, using the Lseg Group Ticker Plant unit header framing.

### Key Characteristics

- **Per service line** - Served by the MiFID II Post Trade market data gateway, so only MiFID II Post Trade messages are carried
- **Rolling cache** - Replays recent application messages by sequence number range
- **Session administration** - Login, replay request and completion messages bracket each retransmission

