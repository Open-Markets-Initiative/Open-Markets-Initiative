## PseEquities News: Pse Equities Itch News

News items of the Philippine Stock Exchange X-stream equities market: the iNav news feed and company disclosures and exchange notices from PSE EDGE.

### Overview

The iNav value of each ETF is sent as a News Item [N] every minute with FirmId EXCH.

Company disclosures and exchange notices are sent as News Item [N] messages; Orderbook is 0 for a listing or disclosure notice. Title, Reference and NewsText are null-terminated and variable length.

Time Stamp - Seconds [T] carries seconds since midnight; every other message carries nanoseconds since the last [T]. The document names no timezone; Asia/Manila is assumed.

Prices are integers scaled by the Price Decimals the Orderbook Directory [R] states for each orderbook: Price = Integer / 10^PriceDecimals.

### Transport

MoldUDP64 provides a sequenced and recoverable UDP multicast stream for one-to-many distribution. The document does not state the MoldUDP64 version. SoupBinTCP v3.0 is the point-to-point transport for Itch payloads; X-stream enforces case-sensitive usernames and passwords in the Login Request Packet. Not modelled in this specification.

