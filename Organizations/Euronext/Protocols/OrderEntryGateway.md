## OrderEntryGateway: Euronext Optiq Order Entry

Binary order entry protocol for submitting and managing orders on Euronext exchanges using Sbe encoding on the Optiq platform.

### Overview

OrderEntryGateway is Euronext's order entry protocol on the Optiq trading platform, providing electronic access for order submission, modification, cancellation, and execution reporting across Euronext's pan-European exchanges. The protocol uses Simple Binary Encoding (Sbe) for compact binary message serialization optimized for low-latency trading.

The protocol supports the full order lifecycle including limit orders, market orders, stop orders, iceberg orders, and pegged orders. Specialized functionality includes mass cancellation, risk controls, market maker quoting, and strategy order entry for multi-leg instruments. OrderEntryGateway covers equities, derivatives, Etfs, bonds, and commodities across all Euronext markets. Execution reports deliver real-time order state transitions including acknowledgments, fills, and rejections.

### Transport

Tcp connections to Euronext Optiq order entry gateways. Sessions are established with authentication and logical access scope. Heartbeat monitoring maintains connection liveness, and message sequencing supports recovery after reconnection.

### Key Characteristics

- **Sbe encoded** - Fixed-position binary fields for deterministic low-latency serialization
- **Optiq platform** - Order entry across Euronext's unified trading platform
- **Pan-European access** - Trading across Paris, Amsterdam, Brussels, Lisbon, Dublin, Oslo, and Milan
- **Multi-asset class** - Equities, derivatives, Etfs, bonds, and commodities
- **Mass operations** - Bulk cancellation by instrument, segment, or session
- **Market maker quoting** - Dedicated quote entry for two-sided pricing
- **Risk controls** - Pre-trade risk checks and kill switch functionality
