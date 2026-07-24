## Securities Combined: Orion Market Data Cash Combined

Hkex Orion Market Data Cash Combined is a superset Reference that lists every message defined in the OMD-C v1.45 specification: framing (Control, Refresh Complete), Reference Data (Market Definition, Security Definition, Liquidity Provider, Currency Rate), Status Data (Trading Session Status, Security Status), the full order-level events (Add Order, Modify Order, Delete Order), the complementary odd-lot events (Add Odd Lot Order, Delete Odd Lot Order), Aggregate Order Book Update, Broker Queue, Order Imbalance, all trade and price messages (Trade, Trade Cancel, Trade Ticker, Closing Price, Nominal Price, Indicative Equilibrium Price, Reference Price, VCM Trigger), Statistics/Market Turnover/Yield, News, Index Definition + Index Data, and the complementary Stock Connect Daily Quota Balance + Market Turnover messages. It is intended for captures that mix feeds or for development/QA where a single dissector is preferred over per-product dissectors.

### Overview

Combined is not a live datafeed product sold by Hkex. It is a convenience aggregation of every OMD-C v1.45 message type into a single Reference so that a Wireshark dissector or parser built from it can decode any captured OMD-C multicast channel regardless of which live product (SS, SP, SF, Index) is subscribed to. It also carries the complementary feeds (Odd Lot Order, Conflated Broker Queue, Stock Connect) that Hkex distributes alongside the four main products.

Because Combined pools every message, it exercises the full enum surface of the spec — including the disambiguated BrokerQueue BQSide field which is renamed from PDF "Side" to avoid enum collision with the Bid/Offer Side used across the other order-book messages.

### Transport

Udp multicast delivery on dual A and B channels with per-channel sequence numbers.

### Key Characteristics

- **Superset dissector** - Single Reference covering every OMD-C v1.45 message
- **Product-agnostic decoding** - Decodes any captured OMD-C channel without knowing which product feeds it
- **Includes complementary feeds** - Odd Lot Order and Stock Connect messages included alongside main-feed messages
- **Includes Index feed** - Index Definition and Index Data messages included alongside security-level messages

