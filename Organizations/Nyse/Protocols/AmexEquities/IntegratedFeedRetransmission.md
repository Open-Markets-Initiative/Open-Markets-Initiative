## AmexEquities Integrated Feed Retransmission: Integrated Feed Retransmission

Retransmission multicast channel replaying missed Integrated Feed messages on request, and publishing Message Unavailable notices, for AmexEquities.

### Transport

Udp multicast for real-time delivery of Pillar binary market data messages with per-packet sequence numbers. Tcp via Pillar stream protocol for retransmission and recovery of missed multicast messages.

