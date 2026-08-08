## TradeEcho Mifid Recovery: MiFID II Post Trade Recovery

Recovery service publishing Trade Echo reference data, instrument status, statistics snapshot and MiFID II trade report messages over a Tcp session using Group Ticker Plant framing.

### Overview

Recovery is the Trade Echo snapshot service, provided over Tcp for subscribers resynchronising after a data loss too large for the replay service. A Recovery Request selects the request level, instrument, segment or multicast channel, and the recovery type, reference data, trades, statistics, instrument status or system event.

The Recovery Response reports the real time channel sequence number the snapshot is synchronised with, so a subscriber buffers later multicast messages and applies them once the snapshot completes. Recovery is the only Trade Echo service line carrying the Statistics Snapshot message, which reports the complete current statistics for an instrument.

### Transport

Tcp unicast session using the Lseg Group Ticker Plant (Gtp) unit header framing, carrying administrative messages and the requested application messages.

### Key Characteristics

- **Snapshot recovery** - Rebuilds reference data, statistics and trade state for an instrument, segment or channel
- **Statistics snapshot** - A single message reports every current statistic calculated for an instrument
- **Synchronisation point** - Responses carry the real time sequence number the snapshot is synchronised to
- **Post trade scope** - Carries the MiFID II Trade Report stream together with reference and status messages

