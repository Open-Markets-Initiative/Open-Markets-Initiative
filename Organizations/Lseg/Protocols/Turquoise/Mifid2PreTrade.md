## Turquoise Mifid2Pre Trade: MiFID II Pre Trade

MiFID II pre trade transparency feed publishing aggregated order book price levels for instruments traded on the Lseg Turquoise Europe Mtf.

### Overview

MiFID II Pre Trade is the Turquoise pre trade transparency service, publishing the aggregated order book required under MiFID II pre trade obligations. Each Order Book Update message reports one price level, giving the side, price, aggregated quantity and the number of orders and quotes standing at that level, together with the venue and the trading system and phase under which the orders are advertised.

The service covers both continuous trading and periodic auctions. Under continuous trading the level identifier gives the position of the price point in the book and a flag marks the last of the top five price points. For periodic auctions the message instead reports the price and quantity that would best satisfy the auction algorithm, and the positional fields carry their default values.

The feed is carried on the Turquoise Europe market data groups only. Regulatory fields use the MiFID ASCII data types, so prices and quantities are published as decimal strings and timestamps in the ISO 8601 MiFID Date and Time form rather than the binary types used by the other Group Ticker Plant service lines.

### Transport

Udp multicast using the Lseg Group Ticker Plant (Gtp) unit header framing, with per packet sequence numbers for gap detection and two identically sequenced feeds for arbitration.

### Key Characteristics

- **Aggregated price levels** - Publishes one message per price level rather than individual orders
- **Pre trade transparency** - Satisfies MiFID II pre trade publication obligations for the order book
- **Continuous and auction** - Covers continuous trading and periodic auction trading systems, indicated per message
- **Regulatory data types** - Prices, quantities and timestamps published in the MiFID ASCII string forms
- **Turquoise Europe** - Carried on the Turquoise Europe market data groups

