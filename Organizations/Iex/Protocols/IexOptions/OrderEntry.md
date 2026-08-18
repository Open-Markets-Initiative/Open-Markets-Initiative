## IexOptions Order Entry: Iex Options Fix Order Entry

Financial Information eXchange (Fix) 4.2 order entry interface for Iex Options carrying order submission, cancel replace, mass cancel with block and unblock, execution reporting, and trade bust and correction messages with Iex custom tags.

### Overview

The Iex Options Fix api is a Fix 4.2 subset for order entry on Iex Options. Members submit single-leg options orders with the full OCC clearing detail (CustomerOrFirm capacity, ClearingFirm, ClearingAccount, OptionalData), anti-internalization qualifiers, and display instructions. Cancel and cancel/replace target working orders while the same message type doubles as a mass cancel with per-MPID or per-session scope, optional symbol filtering, and block and unblock semantics.

Execution reports cover acknowledgement, rejection, cancel, fills with contra party and OCC clearing attribution, replace, unsolicited repricing driven by price adjust and drill-through protection, pending states for routed orders, and mass cancel acknowledgement. A custom UCC message reports trade busts and corrections, and nanosecond-precision custom timestamps accompany every outbound event.

### Transport

Tcp for authenticated Fix 4.2 sessions with sequence-number gap recovery via Resend Request and Sequence Reset.

### Key Characteristics

- **Fix 4.2 session** - Standard Fix session layer with logon, heartbeat, and resend recovery
- **Options order entry** - Single-leg options orders with OSI series identification
- **OCC clearing detail** - Capacity, clearing firm, MMID, and optional data passed to the OCC
- **Mass cancel** - Session or MPID scope with symbol filter, block, and unblock
- **Trade bust and correction** - Custom UCC message reporting busts and corrections with contra detail
- **Nanosecond timestamps** - Custom sending and transact times with nanosecond resolution

