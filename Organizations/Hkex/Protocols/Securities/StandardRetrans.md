## Securities Standard Retrans: Orion Market Data Cash Standard Retransmission

TCP unicast retransmission and refresh service for OMD-C Standard (SS) subscribers. Carries Logon, Logon Response, Retransmission Request, and Retransmission Response messages, plus retransmitted payload messages on the refresh channel. The TCP-carrying packet header is byte-identical to the UDP multicast header (16 bytes; SeqNum and SendTime set to 0 per §3.5).

### Overview

Companion protocol to Hkex.OmdcStandard (UDP multicast market data). Same wire format, different transport and message set — carries only the session-management and retransmission control messages plus their replayed payloads.

### Transport

Tcp unicast recovery service for requesting missed messages by sequence number.

