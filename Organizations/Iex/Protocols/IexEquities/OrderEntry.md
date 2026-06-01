## IexEquities Order Entry: Investors Exchange Fix Order Entry

Fix-based order entry protocol for submitting, modifying, and cancelling equity orders on the Investors Exchange.

### Overview

OrderEntry is the Investors Exchange Fix order entry protocol, providing members with an industry-standard tag-value interface to submit, modify, and cancel orders for Nms equities. Iex implements the standard Fix 4.2 / 4.4 session and application layers extended with Iex-specific order types, time-in-force values, and pegging options.

The protocol supports the full order lifecycle including new order single, order cancel request, order cancel replace request, mass cancel, and execution reports. Sessions are authenticated and provide standard Fix sequence-based recovery with resend request and gap fill messages.

### Transport

Tcp Fix session for persistent authenticated order flow with sequence tracking, heartbeats, and reliable recovery.

### Key Characteristics

- **Industry-standard Fix** - Tag-value Fix protocol session and application layers
- **Full order lifecycle** - New, replace, cancel, mass cancel, and execution report messages
- **Iex-specific extensions** - Iex order types, time-in-force, and discretionary pegging
- **Session based** - Persistent authenticated Fix session per member
- **Sequence recovery** - Standard Fix resend request and gap fill recovery

