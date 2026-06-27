## LtseEquities Order Entry: Ltse Fix Order Entry

Financial Information eXchange (Fix) order entry protocol for the Long-Term Stock Exchange, used by members to submit, modify and cancel orders and receive execution reports over the Memx-Tcp Fix session.

### Overview

The Long-Term Stock Exchange runs on Members Exchange (Memx) trading technology; this is the tag-value Fix Order Entry interface, a standard Fix 4.2 session (Logon, Heartbeat, Test Request, Resend Request, Sequence Reset, Logout) carrying the order lifecycle and execution report messages.

### Transport

Tcp Fix session over the Memx-Tcp channel with sequence tracking, heartbeats, and resend-based recovery.

### Key Characteristics

- **Fix** - Tag-value Financial Information eXchange Order Entry interface
- **Session based** - Persistent authenticated Tcp Fix session per member

