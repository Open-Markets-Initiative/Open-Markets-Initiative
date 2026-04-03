## MarketDataGateway: Euronext Optiq Market Data

Binary market data protocol for disseminating real-time order book and trade data from Euronext exchanges using Sbe encoding on the Optiq platform.

### Overview

MarketDataGateway is Euronext's market data distribution protocol on the Optiq trading platform, delivering real-time book depth, trade reports, instrument reference data, and market status for all instruments traded across Euronext's pan-European exchanges. The protocol uses Simple Binary Encoding (Sbe) for efficient fixed-position binary message serialization.

The feed provides full depth of book with aggregate price level updates, trade ticks, opening and closing auction data, index values, and instrument trading status changes. MarketDataGateway covers equities, bonds, Etfs, derivatives, commodities, and structured products across Euronext's Paris, Amsterdam, Brussels, Lisbon, Dublin, Oslo, and Milan markets. The Sbe encoding delivers deterministic message layouts defined by Xml schema templates.

### Transport

Udp multicast delivery organized by market segment and product group. Real-time incremental feeds carry book and trade updates, while reference data and recovery feeds provide full instrument state. Sequence numbers enable gap detection across multicast groups.

### Key Characteristics

- **Sbe encoded** - Fixed-position binary fields defined by Xml schema templates
- **Optiq platform** - Market data from Euronext's unified trading platform
- **Pan-European coverage** - Instruments across Paris, Amsterdam, Brussels, Lisbon, Dublin, Oslo, and Milan
- **Full depth of book** - Aggregate price level updates for order book reconstruction
- **Multi-asset class** - Equities, derivatives, Etfs, bonds, commodities, and structured products
- **Auction data** - Opening, closing, and intraday auction indicative and result messages
- **Sequenced multicast** - Sequence numbers for gap detection and recovery
