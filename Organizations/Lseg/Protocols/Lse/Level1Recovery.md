## Lse Level1Recovery: Level 1 Recovery

Recovery service for the London Stock Exchange Level 1 market data gateway, carrying the consolidated best bid and offer over a Tcp session using Group Ticker Plant framing.

### Overview

Level 1 Recovery is the snapshot service provided by the Lseg Group Ticker Plant Level 1 market data gateway for London Stock Exchange. The snapshot returned is that of the Level 1 service line, dependent upon the recovery service targeted by the request, so a session rebuilds state from the consolidated best bid and offer.

The Recovery Response reports the real time channel sequence number the snapshot is synchronised with, so a subscriber buffers later multicast messages and applies them once the snapshot completes. Every recovery gateway also serves the Instrument Directory Equities reference data record and the Statistics Snapshot, which are not available on the real time channels.

### Transport

Tcp unicast session to the Level 1 market data gateway, using the Lseg Group Ticker Plant unit header framing.

### Key Characteristics

- **Per service line** - Served by the Level 1 market data gateway, so only Level 1 messages are carried
- **Snapshot recovery** - Rebuilds instrument, segment or channel level state from scratch
- **Synchronisation point** - Responses carry the real time sequence number the snapshot is synchronised to

