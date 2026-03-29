## Mdf: Imperative IntelligentCross Market Data Feed

Market data protocol for disseminating trade and auction information from the IntelligentCross alternative trading system.

### Overview

Mdf is the market data feed for Imperative Execution's IntelligentCross venue, an alternative trading system that uses machine learning to optimize trade timing. The protocol delivers trade reports, auction notifications, and system events to market data consumers. IntelligentCross conducts frequent intraday auctions using an intelligent matching algorithm, and Mdf disseminates the results of these auctions in real time.

The feed provides trade price, size, and execution details for completed auction crosses, along with system status and administrative messages. Mdf enables subscribers to monitor IntelligentCross trading activity and track execution outcomes from the venue's periodic crossing events throughout the trading day.

### Transport

Udp multicast. Messages are delivered over sequenced Udp multicast with framing that supports gap detection and session management for reliable market data consumption.

### Key Characteristics

- **IntelligentCross trades** - Real-time dissemination of auction cross execution results
- **Auction-based venue** - Data reflects frequent intraday machine learning-optimized auctions
- **Trade reports** - Provides price, size, and execution details for completed crosses
- **System events** - Administrative messages for session state and trading status
- **Sequenced delivery** - Messages carry sequence numbers for gap detection
- **Low message rate** - Periodic auction results rather than continuous order book updates
