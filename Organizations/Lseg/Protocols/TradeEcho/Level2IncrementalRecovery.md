## TradeEcho Level2Incremental Recovery: Level 2 Incremental Recovery

Recovery service publishing Trade Echo reference data, instrument status and Systematic Internaliser quote book snapshots over a Tcp session using Group Ticker Plant framing.

### Overview

Recovery is the Trade Echo snapshot service, provided over Tcp for subscribers resynchronising after a data loss too large for the replay service. A Recovery Request selects the request level, instrument, segment or multicast channel, and the recovery type, reference data, order book, instrument status or system event.

The Recovery Response reports the real time channel sequence number the snapshot is synchronised with, so a subscriber buffers later multicast messages and applies them once the snapshot completes. The quote book is rebuilt from SI Quote messages, with Order Book Clear delimiting each instrument; Order Delete is not republished on recovery because the snapshot already reflects the resting quotes.

### Transport

Tcp unicast session using the Lseg Group Ticker Plant (Gtp) unit header framing, carrying administrative messages and the requested application messages.

### Key Characteristics

- **Snapshot recovery** - Rebuilds reference data, instrument status and quote book state for an instrument, segment or channel
- **Quote book rebuild** - Resting Systematic Internaliser quotes are replayed as SI Quote messages rather than incremental deltas
- **Synchronisation point** - Responses carry the real time sequence number the snapshot is synchronised to
- **Pre trade scope** - Carries the Systematic Internaliser quote stream together with reference and status messages

