## CxjSor Order Entry: Cboe Japan SOR Fix order entry

Financial Information eXchange (Fix) order entry protocol for submitting, modifying, and cancelling orders on Cboe Japan SOR, covering new order, order cancel, order cancel/replace, execution report, and cancel reject messages.

### Overview

Order Entry is the Fix order port for Cboe Japan SOR, providing members a tag-value interface to submit, modify, and cancel orders and receive execution reports over a standard Fix session (Logon, Heartbeat, Test Request, Resend Request, Sequence Reset, Logout).

The protocol covers the full order lifecycle — new order single, order cancel request, order cancel/replace request, execution report, cancel reject, and trade cancel/correct.

### Transport

Tcp Fix session per member with sequence tracking, heartbeats, and resend-based recovery.

### Key Characteristics

- **Fix** - Tag-value Financial Information eXchange order entry
- **Full order lifecycle** - New, cancel, cancel/replace, execution report, cancel reject
- **Session based** - Persistent authenticated Tcp Fix session per member
- **Sequence recovery** - Resend Request / Sequence Reset gap recovery

