## C1Options Complex Options Futures: Complex Options Futures

Complex Options/Futures multicast market data feed for Cboe C1 Options Exchange, carrying only complex options orders with futures legs.

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of sequenced binary market data messages with per-packet sequence numbers and A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover messages missed on the multicast feed.

