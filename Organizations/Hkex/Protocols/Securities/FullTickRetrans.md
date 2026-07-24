## Securities Full Tick Retrans: Orion Market Data Cash FullTick Retransmission

TCP unicast retransmission and refresh service for OMD-C FullTick (SF) subscribers. Carries Logon, Logon Response, Retransmission Request, and Retransmission Response messages, plus retransmitted payload messages on the refresh channel. The TCP-carrying packet header is byte-identical to the UDP multicast header (16 bytes; SeqNum and SendTime set to 0 per §3.5).

### Overview

Companion protocol to Hkex.OmdcFullTick (UDP multicast market data). Same wire format, different transport and message set — carries only the session-management and retransmission control messages plus their replayed payloads.

### Transport

Tcp unicast recovery service for requesting missed messages by sequence number.

