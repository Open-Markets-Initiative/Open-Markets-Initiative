## Risk Control: Memx Options Risk Controls

Sbe-encoded protocol for managing pre-trade and post-trade risk controls on Memx options markets.

### Overview

Risk Control is the Memx risk management protocol providing configurable risk limits and automated protective actions for options trading. The protocol uses Simple Binary Encoding (Sbe) to deliver risk parameter configuration, threshold monitoring, and kill switch functionality for options market participants.

The protocol enables firms to set and manage risk thresholds including notional limits, contract limits, and rate controls for their options order flow. When configured thresholds are breached, the system can automatically cancel open orders and block new order submissions. Risk Control supports both self-imposed firm-level controls and exchange-imposed regulatory risk limits.

### Transport

Tcp to Memx risk management gateways. Sessions use the Memx common header framework with sequenced message delivery.

### Key Characteristics

- **Sbe encoded** - Fixed-position, fixed-length fields for zero-copy parsing
- **Options risk management** - Pre-trade and post-trade controls for options
- **Configurable thresholds** - Notional, contract, and rate-based risk limits
- **Kill switch** - Automated order cancellation on threshold breach
- **Firm-level controls** - Self-imposed and exchange-imposed risk parameters
- **Real-time monitoring** - Continuous risk exposure tracking and alerting
