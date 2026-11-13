## PseEquities Total View: Pse Equities Itch Total View

Order level market data of the Philippine Stock Exchange X-stream equities market: reference data, every order added, executed, replaced and deleted, auction indications and trades.

### Overview

When the market has Broker Anonymity the feed sends Order Executed [E], Order Executed With Price [C] and Trade [P]; without it, the (with Broker ID) variants [e], [c] and [p].

An Add Order [A] with Order Number and Quantity both zero carries the orderbook's reference price. A Trade [P] or [p] with Match Number and Executed Quantity both zero carries its close price.

Trade [P] and [p] publish only intentional cross, block and manually entered trades; auction and continuous executions arrive as Order Executed With Price and Order Executed.

Time Stamp - Seconds [T] carries seconds since midnight; every other message carries nanoseconds since the last [T]. The document names no timezone; Asia/Manila is assumed.

Prices are integers scaled by the Price Decimals the Orderbook Directory [R] states for each orderbook: Price = Integer / 10^PriceDecimals.

### Transport

MoldUDP64 provides a sequenced and recoverable UDP multicast stream for one-to-many distribution. The document does not state the MoldUDP64 version. SoupBinTCP v3.0 is the point-to-point transport for Itch payloads; X-stream enforces case-sensitive usernames and passwords in the Login Request Packet. Not modelled in this specification.

