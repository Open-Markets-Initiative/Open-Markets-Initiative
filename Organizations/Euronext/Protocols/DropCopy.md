## DropCopy: Euronext Optiq Post-Trade

Binary post-trade protocol for receiving execution reports and order activity from Euronext exchanges using Sbe encoding on the Optiq platform.

### Overview

DropCopy is Euronext's post-trade data feed on the Optiq platform, providing a secondary stream of execution reports, order acknowledgments, and trade notifications for monitoring and compliance purposes. The protocol uses Simple Binary Encoding (Sbe) consistent with the OrderEntryGateway, delivering a real-time copy of all trading activity associated with a participant's sessions.

The feed delivers execution messages including fills, partial fills, cancellations, and order state changes across all instruments and markets accessible through the participant's trading configuration. DropCopy enables middle and back-office systems, risk management platforms, and compliance monitors to independently track trading activity without interfering with the primary order entry path. The feed covers all asset classes available on Euronext's Optiq platform.

### Transport

Tcp connections to Euronext Optiq drop copy gateways. Sessions are established with authentication and scoped to the participant's firm or trading group. Message sequencing supports reliable delivery and recovery of execution data.

### Key Characteristics

- **Sbe encoded** - Fixed-position binary fields consistent with Optiq order entry messages
- **Post-trade feed** - Secondary stream of execution reports independent of order entry
- **Full activity coverage** - Fills, cancellations, acknowledgments, and order state changes
- **Multi-asset class** - Execution data across equities, derivatives, Etfs, bonds, and commodities
- **Compliance monitoring** - Independent trade activity stream for surveillance and risk
- **Firm-scoped** - Activity across all sessions associated with the participant's configuration
- **Sequenced delivery** - Message sequencing for reliable gap detection and recovery
