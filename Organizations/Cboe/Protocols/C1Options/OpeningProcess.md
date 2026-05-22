## C1Options Opening Process: Cboe C1 Options Opening Process

Cboe Titanium C1 Options Opening Process Pitch feed publishing the open-auction process events for options listed on Cboe Options Exchange (C1). Two WAN-Shaped multicast feeds (CCO/CDO) for A/B redundancy plus a Cert feed.

### Transport

Udp multicast via the Cboe Pitch framing for real-time delivery of sequenced binary market data messages with per-packet sequence numbers and A and B feed redundancy. Tcp for the Cboe Grp Gap Request Proxy service used by subscribers to recover messages missed on the multicast feed.

