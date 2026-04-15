## NomOptions Bono: Nasdaq Options Binary Order Entry

Binary order entry protocol for submitting, modifying, and cancelling options orders on the Nasdaq Options Market.

### Overview

Bono is the binary order entry protocol for the Nasdaq Options Market (Nom), providing members with a low-latency session-based interface to submit, modify, and cancel options orders. The wire format uses compact fixed-width binary messages framed by SoupBinTcp for session authentication and recovery.

### Transport

Tcp via SoupBinTcp for persistent authenticated sessions carrying Nasdaq Options binary order entry messages with sequence recovery.

### Key Characteristics

- **Nasdaq Options** - Nom options order entry
- **SoupBinTcp framed** - Session authentication and sequence recovery
- **Binary encoded** - Fixed-width low latency messages
- **Full order lifecycle** - New, modify, cancel, and execution report messages
- **Session based** - Persistent authenticated Tcp session per member

