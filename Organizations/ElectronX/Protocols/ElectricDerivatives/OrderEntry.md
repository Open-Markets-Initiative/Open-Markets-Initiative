## ElectricDerivatives Order Entry: ElectronX Fix 5.0 Order Entry (NLS)

Fix 5.0 (SP2) order entry gateway, the ElectronX Native Limit System (NLS), providing order entry, modification, cancellation, and execution reporting for the bounded futures and binary options listed on the ElectronX electronic exchange.

### Overview

The ElectronX Order Entry interface is the Native Limit System (NLS), a Fix 5.0 (Service Pack 2) order entry gateway for the ElectronX electronic exchange. It gives trading firms a standards-based tagged-value channel for the full order lifecycle on ElectronX's bounded futures and binary options, including new order entry, modification, cancellation, and the corresponding execution reports.

Sessions are established with a standard Fix Logon and maintained with heartbeats and test requests; sequence numbers are tracked bidirectionally and missed messages are recovered through resend requests. The gateway exposes ElectronX-specific order handling and instrument semantics through the Fix message set, delivering acknowledgements, fills, and rejects on the same session used to submit orders.

### Transport

Tcp for persistent authenticated Fix 5.0 SP2 sessions carrying order entry, modification, cancellation, and execution report messages with bidirectional sequence numbering and gap recovery.

### Key Characteristics

- **Fix 5.0 SP2** - Standards-based tagged-value order entry over Tcp
- **Native Limit System** - The NLS order entry gateway for the ElectronX exchange
- **Full order lifecycle** - New, modify, cancel, and execution report messages
- **Bounded futures** - Order entry for ElectronX bounded futures contracts
- **Binary options** - Order entry for ElectronX binary options
- **Session based** - Authenticated Fix session with bidirectional sequence tracking and gap recovery

