## Turquoise Recovery: Recovery

Recovery service publishing Turquoise reference data, instrument status, order book and trade snapshots for any real time service line over a Tcp session using Group Ticker Plant framing.

### Overview

Recovery is the Turquoise snapshot service, provided over Tcp for subscribers resynchronising after a data loss too large for the replay service. A Recovery Request selects the request level, instrument, segment or multicast channel, and the recovery type, reference data, order book, trades, statistics, instrument status or system event.

The Recovery Response reports the real time channel sequence number the snapshot is synchronised with, so a subscriber buffers later multicast messages and applies them once the snapshot completes. Recovery substitutes two snapshot forms for their real time counterparts, Instrument Directory Equities in place of Instrument Directory and Statistics Snapshot in place of Statistics.

### Transport

Tcp unicast session using the Lseg Group Ticker Plant (Gtp) unit header framing, carrying administrative messages and the requested application messages.

### Key Characteristics

- **Snapshot recovery** - Rebuilds reference data, instrument status and order book state for an instrument, segment or channel
- **Snapshot message forms** - Instrument Directory Equities and Statistics Snapshot replace their incremental counterparts
- **Synchronisation point** - Responses carry the real time sequence number the snapshot is synchronised to
- **Shared across service lines** - A single recovery channel per market data group serves Level 1, Level 2 Incremental, MiFID II Post Trade and Analytics

