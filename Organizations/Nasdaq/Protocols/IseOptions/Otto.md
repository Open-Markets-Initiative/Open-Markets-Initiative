## IseOptions Otto: Ise Options Order Entry

Ouch-based binary order entry protocol for submitting, modifying, and cancelling options orders on the Nasdaq Ise Options Exchange.

### Overview

Ouch-based binary order entry protocol for submitting, modifying, and cancelling options orders on the Nasdaq Ise Options Exchange

### Transport

Tcp via SoupBinTcp for persistent authenticated sessions carrying order entry, modification, cancellation, and execution report messages.

### Key Characteristics

- **Nasdaq Ouch** - Industry-standard Ouch order entry
- **SoupBinTcp framed** - Session recovery and heartbeat
- **Options order entry** - Full order lifecycle
- **Session based** - Persistent authenticated session per member
- **Binary encoded** - Fixed-width low latency messages

