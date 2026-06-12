## TitaniumConsolidated One Equities: One Equities

Cboe One Equities — consolidated equities market data feed combining top of book, last sale, and auction information across the four Cboe US equities exchanges (BZX, BYX, EDGA, EDGX).

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of sequenced binary market data messages with per-packet sequence numbers and A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover messages missed on the multicast feed.

