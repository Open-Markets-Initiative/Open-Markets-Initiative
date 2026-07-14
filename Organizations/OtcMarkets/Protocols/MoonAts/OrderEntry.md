## MoonAts Order Entry: MOON ATS FIX order entry for overnight NMS trading

FIX 4.2 order entry interface for MOON ATS (Markets Open Overnight), OTC Markets Group's SEC registered alternative trading system for extended overnight trading of NMS-listed US equity securities. Subscribers submit New Order Single, Order Cancel Request, and Order Cancel/Replace Request messages and receive Execution Reports and Order Cancel Rejects over an authenticated FIX session.

### Overview

MOON FIX is the order entry interface for MOON ATS overnight trading sessions (18:00 to 04:00 Eastern). The message vocabulary is the standard FIX 4.2 order lifecycle: New Order Single, Order Cancel Request, Order Cancel/Replace Request inbound; Execution Report and Order Cancel Reject outbound.

Orders support self trade prevention (ExecInst 18=a with optional NoSelfTrade tag 7928), the IOC after Cancel/Replace execution instruction, and the Route Outside Normal Market Hours instruction. Order entry price precision is limited to 2 decimal places at or above $1.00.

### Transport

Persistent authenticated FIX 4.2 session over Tcp with standard sequence-number recovery; messages queued prior to initial connection are not delivered.

### Key Characteristics

- **Fix 4.2** - Industry-standard tag-value order entry over an authenticated Tcp session
- **Overnight NMS trading** - Order entry for MOON ATS sessions running 18:00 to 04:00 Eastern
- **Full order lifecycle** - New Order Single, Cancel, Cancel/Replace, Execution Report, and Cancel Reject
- **Self trade prevention** - ExecInst 18=a with optional NoSelfTrade tag 7928 per-firm configuration
- **Price precision rules** - Up to 2 decimal places at or above $1.00, finer precision below

