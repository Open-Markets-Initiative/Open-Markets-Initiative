## CboeEurope Cedx: Cboe Europe Derivatives Binary Order Entry

Cboe Binary Order Entry protocol for submitting orders on the Cboe Europe Derivatives Exchange single-stock futures and equity index options markets.

### Overview

Cedx is the order entry interface for Cboe Europe Derivatives Exchange, the Cboe European futures and options venue. It uses the same Cboe Binary Order Entry (Boe) session layer and message family as the US equities and options markets, providing members with a consistent low-latency interface for submitting, modifying, and cancelling orders on Cboe-listed single stock futures and equity index options.

### Transport

Tcp via the Cboe Boe session layer for persistent authenticated order flow to the Cedx matching engine.

### Key Characteristics

- **Cboe Boe** - Native Cboe Binary Order Entry protocol
- **European derivatives** - Single stock futures and equity index options
- **Session based** - Persistent authenticated Tcp session per member
- **Full order lifecycle** - New, modify, cancel, and execution report messages
- **Consistent with US markets** - Shared message model across Cboe venues

