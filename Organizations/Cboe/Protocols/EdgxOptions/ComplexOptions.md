## EdgxOptions Complex Options: Cboe EDGX Options Complex Order Entry

Cboe Binary Order Entry protocol for submitting, modifying, and cancelling complex multi-leg orders on Cboe EDGX Options Exchange.

### Overview

Complex Options is the Cboe Binary Order Entry variant for complex multi-leg strategies on Cboe EDGX Options Exchange. It extends the standard Boe protocol with message types for defining and submitting spreads, straddles, combinations, and other multi-leg strategies, along with the order lifecycle messages needed to manage them.

The protocol runs over Tcp using the Boe session layer for authentication, sequence tracking, and recovery. Execution reports for complex orders include per-leg details so that clients can allocate fills back to the individual strategy components.

### Transport

Tcp via the Cboe Binary Order Entry (Boe) session layer for persistent authenticated order flow with sequence tracking, heartbeats, and reliable recovery.

### Key Characteristics

- **Complex order entry** - Multi-leg strategy submission and management
- **Per-leg fills** - Execution reports with per-leg allocation details
- **Cboe Boe** - Native Cboe Binary Order Entry protocol
- **Session based** - Persistent authenticated Tcp session per member
- **Strategy definitions** - Support for ad-hoc and pre-defined strategies

