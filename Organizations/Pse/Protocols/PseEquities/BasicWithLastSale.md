## PseEquities Basic With Last Sale: Pse Equities Itch Basic With Last Sale

Top of book and last sale market data of the Philippine Stock Exchange X-stream equities market: reference data, best bid and offer quotations and every trade.

### Overview

A BBO Quotation [O] with Best Bid Size and Best Offer Size both 0x7FFFFFFFFFFFFFFF carries the orderbook's reference price in Best Bid Price.

Trade [P] and [p] publish all trades on this feed; a Trade with Match Number and Executed Quantity both zero carries the close price.

Time Stamp - Seconds [T] carries seconds since midnight; every other message carries nanoseconds since the last [T]. The document names no timezone; Asia/Manila is assumed.

Prices are integers scaled by the Price Decimals the Orderbook Directory [R] states for each orderbook: Price = Integer / 10^PriceDecimals.

### Transport

MoldUDP64 provides a sequenced and recoverable UDP multicast stream for one-to-many distribution. The document does not state the MoldUDP64 version. SoupBinTCP v3.0 is the point-to-point transport for Itch payloads; X-stream enforces case-sensitive usernames and passwords in the Login Request Packet. Not modelled in this specification.

