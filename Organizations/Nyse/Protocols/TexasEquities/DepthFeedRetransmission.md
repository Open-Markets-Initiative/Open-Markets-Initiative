## TexasEquities Depth Feed Retransmission: Depth Feed Retransmission

Retransmission multicast channel replaying missed Depth Feed messages on request, and publishing Message Unavailable notices, for Nyse Texas Equities.

### Transport

Udp multicast for real-time delivery of Pillar binary market data messages with per-packet sequence numbers. Tcp via Pillar stream protocol for retransmission and recovery of missed multicast messages.

