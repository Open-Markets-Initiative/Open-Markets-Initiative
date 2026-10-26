## Spectra Orders Log Replay: SIMBA Spectra Orders Log Historical Replay

Historical replay of the current trading session over a Tcp session, the second of the two recovery paths and the one for small gaps. The firm logs on, requests a range with a market data request, and the gateway answers with the same best prices, empty book, order update and order execution messages it had already multicast. The firm and the gateway send different message sets over the one session, so each direction is modelled as its own packet root.

### Transport

A Tcp session: the firm logs on, asks for a range with a market data request, and the gateway replays the incremental messages in snapshot packet framing before the firm logs out.

### Key Characteristics

- **Session recovery** - Replays the current trading session for a bounded gap
- **Bidirectional** - The firm logs on and requests; the gateway replays
- **Snapshot framing** - Both directions carry one Sbe message per packet header
- **Simple Binary Encoding** - Fix messages encoded to the Sbe version 1 standard against a published schema
- **Request bounded** - A market data request names the sequence range to replay

