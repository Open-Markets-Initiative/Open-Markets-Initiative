## Cboe Europe Trf Order Entry

Boe binary order entry protocol for trade reporting facility submissions on Cboe European venues.

### Overview

Europe Trf Order Entry provides order entry specifically for the Cboe Europe Trade Reporting Facility using the Boe binary protocol. The protocol enables participants to submit trade reports for off-exchange transactions that require publication through Cboe Europe's Trf.

The protocol handles trade report submission, amendment, and cancellation for Otc transactions. It supports the regulatory requirement for post-trade transparency by providing an efficient mechanism for reporting off-venue executions through Cboe Europe's infrastructure.

### Transport

Tcp connections to Cboe Europe Trf gateways with session authentication and heartbeat management.

### Key Characteristics

- **Trade reporting** - Submission of off-exchange trade reports to Cboe Europe Trf
- **Binary encoded** - Compact Boe message format for efficient report submission
- **Report management** - Amendment and cancellation of previously submitted trade reports
- **Post-trade transparency** - Supports regulatory publication requirements for Otc transactions
