## HkexDerivatives Premium Retrans: Orion Market Data Derivatives Premium Retransmission

TCP unicast retransmission service for the OMD-D Premium product. Carries Logon, Logon Response, Retransmission Request, and Retransmission Response messages plus retransmitted payload messages. The TCP packet header is byte-identical to the UDP multicast header (16 bytes; SeqNum and SendTime set to 0 per the OMD-D spec).

### Transport

Tcp unicast recovery service for requesting missed messages by sequence number.

