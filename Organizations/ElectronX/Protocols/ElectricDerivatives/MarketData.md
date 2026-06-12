## ElectricDerivatives Market Data: ElectronX Fix 5.0 Market Data

Fix 5.0 (SP2) market data feed for the ElectronX electronic exchange, disseminating quotes, trades, and instrument status for its bounded futures and binary options over a tagged-value Fix session.

### Overview

The ElectronX Market Data interface is a Fix 5.0 (Service Pack 2) feed that disseminates real-time market data for the bounded futures and binary options listed on the ElectronX electronic exchange. It delivers quotes, trade prints, and instrument and security status updates as standard Fix tagged-value messages, providing a standards-based alternative for firms that already integrate with the ElectronX order entry gateway.

The feed is delivered over authenticated Fix sessions using standard market data subscription and incremental refresh messages, with sequence numbers tracked for reliable delivery and gap recovery. It shares instrument identification and field semantics with the ElectronX Native Limit System order entry gateway.

### Transport

Tcp for authenticated Fix 5.0 SP2 market data sessions delivering quote, trade, and security status messages with sequence-numbered reliable delivery.

### Key Characteristics

- **Fix 5.0 SP2** - Standards-based tagged-value market data over Tcp
- **Quotes and trades** - Real-time quote updates and trade prints
- **Security status** - Instrument and session-level status updates
- **Bounded futures** - Market data for ElectronX bounded futures contracts
- **Binary options** - Market data for ElectronX binary options
- **Authenticated sessions** - Standard Fix login over Tcp with sequence tracking

