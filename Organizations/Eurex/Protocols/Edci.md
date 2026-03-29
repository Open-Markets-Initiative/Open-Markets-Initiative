## Edci: Enhanced Derivatives Clearing Interface

Binary market data protocol providing clearing-related data from the Eurex T7 platform for derivatives instruments.

### Overview

Edci (Enhanced Derivatives Clearing Interface) is Deutsche Boerse's data interface for disseminating clearing-related information from the T7 platform. The protocol delivers real-time and end-of-day data relevant to the clearing lifecycle of derivatives instruments traded on Eurex, including settlement prices, margin parameters, position data, and clearing reference information.

Edci serves clearing members, risk managers, and back-office systems that require timely access to clearing-specific data beyond what standard market data feeds provide. The interface covers derivatives products cleared through Eurex Clearing, providing the data necessary for position management, margin calculation, and settlement processing within the T7 ecosystem.

### Transport

Tcp connections to T7 clearing data gateways. Session management provides authentication and sequenced message delivery for reliable data consumption.

### Key Characteristics

- **T7 platform** - Clearing data from Eurex derivatives and the T7 clearing infrastructure
- **Settlement prices** - Daily and intraday settlement price dissemination
- **Margin parameters** - Risk parameters for margin calculation and risk management
- **Derivatives clearing** - Focused on the clearing lifecycle of Eurex derivatives products
- **Position data** - Clearing-related position information for members
- **Reference data** - Clearing instrument definitions and contract parameters
