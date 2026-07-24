## Securities Combined Retrans: Orion Market Data Cash Combined Retransmission

TCP unicast retransmission and refresh service for OMD-C subscribers, superset variant. Carries Logon, Logon Response, Retransmission Request, and Retransmission Response messages, plus retransmitted payload messages spanning every OMD-C product's message set on the refresh channel. The TCP-carrying packet header is byte-identical to the UDP multicast header (16 bytes; SeqNum and SendTime set to 0 per §3.5).

### Overview

Companion protocol to Hkex.OmdcCombined (UDP multicast superset). Same wire format, different transport — used to decode captures of the TCP retrans stream when it may replay messages from any OMD-C product family.

### Transport

Tcp unicast recovery service for requesting missed messages by sequence number.

