## NomOptions Quoting: Nasdaq Options Market (NOM) Specialized Quote Interface (SQF)

Binary market maker quoting interface for bulk quotes, purges and reentry, risk parameter configuration and market sweeps and auction responses on Nasdaq Options Market (NOM).

### Overview

SQF gives market makers a low latency, high throughput quoting path that resides on the matching engine infrastructure. Quote blocks carry up to 200 two-sided quotes for simple or complex instruments, and every quote acknowledgement carries the matching engine sequence of the quote so ordering between quotes and purges within an underlying can be determined.

Risk protection is configured per underlying through Rapid Fire/Curtailment or ActiveQP/Self-Replenishment parameters; purges and reentry work per underlying and instrument type. Market Sweep and Auction Response (MSAR) requests access liquidity or answer auctions, and optional notifications report instrument directories, trading actions, auctions, purges and quote and MSAR executions.

### Transport

Tcp via SoupBinTcp 4.10; client requests are unsequenced data packets and the SQF host answers with sequenced (recoverable) or unsequenced (best effort) data packets.

### Key Characteristics

- **Bulk quoting** - Up to 200 simple or complex quotes per quote block
- **Deterministic acknowledgements** - Matching engine sequence returned for every quote and purge
- **Risk protection** - Rapid Fire/Curtailment and ActiveQP self-replenishment
- **SoupBinTcp 4.10 framed** - Sequenced and unsequenced server messages
- **Two character message types** - Type/Subtype message identifiers

