## PseEquities Index: Pse Equities Itch Index

Index market data of the Philippine Stock Exchange X-stream equities market: index composition and index values.

### Overview

Index composition is defined by Index Member Directory [Y] messages, sent on this feed only.

Time Stamp - Seconds [T] carries seconds since midnight; every other message carries nanoseconds since the last [T]. The document names no timezone; Asia/Manila is assumed.

Prices are integers scaled by the Price Decimals the Orderbook Directory [R] states for each orderbook: Price = Integer / 10^PriceDecimals.

### Transport

MoldUDP64 provides a sequenced and recoverable UDP multicast stream for one-to-many distribution. The document does not state the MoldUDP64 version. SoupBinTCP v3.0 is the point-to-point transport for Itch payloads; X-stream enforces case-sensitive usernames and passwords in the Login Request Packet. Not modelled in this specification.

