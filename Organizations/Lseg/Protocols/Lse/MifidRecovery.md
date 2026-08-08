## Lse Mifid Recovery: MiFID II Post Trade Recovery

Recovery service for the London Stock Exchange MiFID II Post Trade market data gateway, carrying MiFID II post trade transparency reports over a Tcp session using Group Ticker Plant framing.

### Overview

MiFID II Post Trade Recovery is the snapshot service provided by the Lseg Group Ticker Plant MiFID II Post Trade market data gateway for London Stock Exchange. The snapshot returned is that of the MiFID II Post Trade service line, dependent upon the recovery service targeted by the request, so a session rebuilds state from MiFID II post trade transparency reports.

The Recovery Response reports the real time channel sequence number the snapshot is synchronised with, so a subscriber buffers later multicast messages and applies them once the snapshot completes. Every recovery gateway also serves the Instrument Directory Equities reference data record and the Statistics Snapshot, which are not available on the real time channels.

### Transport

Tcp unicast session to the MiFID II Post Trade market data gateway, using the Lseg Group Ticker Plant unit header framing.

### Key Characteristics

- **Per service line** - Served by the MiFID II Post Trade market data gateway, so only MiFID II Post Trade messages are carried
- **Snapshot recovery** - Rebuilds instrument, segment or channel level state from scratch
- **Synchronisation point** - Responses carry the real time sequence number the snapshot is synchronised to

