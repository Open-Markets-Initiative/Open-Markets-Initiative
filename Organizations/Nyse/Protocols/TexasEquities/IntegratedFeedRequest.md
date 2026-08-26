## TexasEquities Integrated Feed Request: Integrated Feed Request

Request channel carrying client retransmission, refresh and symbol index mapping requests and the corresponding server responses for TexasEquities.

### Transport

Udp multicast for real-time delivery of Pillar binary market data messages with per-packet sequence numbers. Tcp via Pillar stream protocol for retransmission and recovery of missed multicast messages.

