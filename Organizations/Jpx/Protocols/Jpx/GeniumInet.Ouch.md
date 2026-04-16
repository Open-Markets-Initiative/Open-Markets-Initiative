## Genium Inet.Ouch: Osaka Securities Exchange Ouch Order Entry

Ouch-based binary order entry protocol for submitting, replacing, and cancelling orders on the Osaka Securities Exchange Jpx Genium Inet platform.

### Overview

Genium Inet Ouch is the order entry protocol for the Japan Exchange Group Osaka Securities Exchange (Ose), providing members with a low-latency binary interface to submit, replace, and cancel orders for derivatives including futures and options. The wire format is the Nasdaq Ouch message family adapted for the Genium Inet platform.

Messages are framed with SoupBinTcp over Tcp which provides session authentication, heartbeat monitoring, and sequence-based recovery. The protocol carries the full order lifecycle including enter, replace, cancel, accepted, rejected, and executed events.

### Transport

Tcp via SoupBinTcp for persistent authenticated Ouch sessions carrying order submission, replacement, cancellation, and execution report messages.

### Key Characteristics

- **Osaka derivatives** - Order entry for futures and options on Jpx Ose
- **Genium Inet platform** - Nasdaq Genium Inet matching engine
- **Ouch encoded** - Nasdaq Ouch binary order entry format
- **SoupBinTcp framed** - Session authentication and sequence recovery
- **Full order lifecycle** - Enter, replace, cancel, and execution reports

