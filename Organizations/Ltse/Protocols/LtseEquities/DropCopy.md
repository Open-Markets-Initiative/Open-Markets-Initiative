## LtseEquities Drop Copy: Ltse Fix Drop Copy

Financial Information eXchange (Fix) drop copy protocol for the Long-Term Stock Exchange, delivering copies of execution reports and order state changes to a member's drop session.

### Overview

The Long-Term Stock Exchange runs on Members Exchange (Memx) trading technology; this is the tag-value Fix Drop Copy interface, a standard Fix 4.2 session (Logon, Heartbeat, Test Request, Resend Request, Sequence Reset, Logout) carrying the order lifecycle and execution report messages.

### Transport

Tcp Fix session over the Memx-Tcp channel with sequence tracking, heartbeats, and resend-based recovery.

### Key Characteristics

- **Fix** - Tag-value Financial Information eXchange Drop Copy interface
- **Session based** - Persistent authenticated Tcp Fix session per member

