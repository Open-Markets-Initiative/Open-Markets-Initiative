## Lse Level2Mbp Recovery: Level 2 MBP Recovery

Recovery service for the London Stock Exchange Level 2 MBP market data gateway, carrying aggregated price points over a Tcp session using Group Ticker Plant framing.

### Overview

Level 2 MBP Recovery is the snapshot service provided by the Lseg Group Ticker Plant Level 2 MBP market data gateway for London Stock Exchange. The snapshot returned is that of the Level 2 MBP service line, dependent upon the recovery service targeted by the request, so a session rebuilds state from aggregated price points.

The Recovery Response reports the real time channel sequence number the snapshot is synchronised with, so a subscriber buffers later multicast messages and applies them once the snapshot completes. Every recovery gateway also serves the Instrument Directory Equities reference data record and the Statistics Snapshot, which are not available on the real time channels.

### Transport

Tcp unicast session to the Level 2 MBP market data gateway, using the Lseg Group Ticker Plant unit header framing.

### Key Characteristics

- **Per service line** - Served by the Level 2 MBP market data gateway, so only Level 2 MBP messages are carried
- **Snapshot recovery** - Rebuilds instrument, segment or channel level state from scratch
- **Synchronisation point** - Responses carry the real time sequence number the snapshot is synchronised to

