## Edci: Eurex T7 Clearing Reference Data

Clearing-oriented reference data and trade information interface for the Eurex T7 platform providing post-trade data for clearing members and risk systems.

### Overview

Edci is the Eurex Extended Derivatives Clearing Interface, a reference data and post-trade messaging channel for the T7 platform. It delivers clearing-relevant events including trade captures, instrument definitions, and position updates to clearing members, settlement systems, and post-trade risk infrastructure.

The protocol uses the T7 binary encoding to keep message processing efficient and consistent with the other T7 interfaces, while targeting the integration needs of the clearing and risk ecosystem rather than pre-trade market data consumption. It provides the authoritative view of executed trades and instrument reference data for downstream post-trade processing.

### Transport

Tcp for authenticated sessions delivering trade capture, position, and reference data messages needed by clearing members and post-trade risk systems.

### Key Characteristics

- **T7 platform** - Native reference data interface for the Eurex T7 trading system
- **Clearing oriented** - Trade captures and position data for clearing members
- **Instrument reference** - Authoritative instrument definitions from the trading system
- **Binary encoded** - Compact fixed-width T7 messages for efficient processing
- **Post-trade focus** - Complements the Eobi market data and Eti order entry interfaces
- **Session based** - Authenticated Tcp session delivery

