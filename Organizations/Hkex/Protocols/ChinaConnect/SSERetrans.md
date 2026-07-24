## ChinaConnect SSERetrans: Orion Market Data China Connect SSE Retransmission

TCP unicast retransmission service for the OMD-CC Shanghai Stock Exchange (SSE A-Share) real-time channel. Carries Logon, Logon Response, Retransmission Request, and Retransmission Response messages plus replayed real-time payload messages.

### Overview

Companion protocol to the SSE real-time UDP feed. Same wire format, different transport and message set — carries session-management and retransmission control messages plus their replayed payloads.

### Transport

Tcp unicast recovery service for the SSE real-time channel.

