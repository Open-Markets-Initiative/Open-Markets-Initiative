## ElectronX Order Entry: ElectronX NLS Fix Order Entry

Fix-based order entry protocol for submitting, modifying, and cancelling Bounded Futures and Binary Options orders on the ElectronX exchange. NLS (Native Limit System) is the ElectronX-branded name for the Fix interface.

### Overview

OrderEntry is delivered via a dedicated Fix gateway separate from the market data session. ElectronX implements the Fix 5.0 SP2 application layer over Fix 5 session level messaging, extended with ElectronX-specific symbology for Bounded Futures and Binary Options instruments.

The protocol supports the full order lifecycle including new order single, order cancel request, order cancel replace request, mass cancel, mass cancel report, and execution reports. Sessions include Cancel-on-Disconnect and Cancel-on-Logout safeguards, and the gateway provides standard Fix sequence-based recovery with resend request, gap fill, and sequence reset messages. Mass Quote Protection (MQP) limits the impact of runaway quoting by auto-cancelling resting orders in a bucket once an executed-quantity threshold is reached within a rolling window.

### Transport

Tcp Fix 5.0 SP2 session for persistent authenticated order flow with sequence tracking, heartbeats, Cancel-on-Disconnect, and reliable recovery.

### Key Characteristics

- **Separate gateway** - Order entry sessions are not accessible via the market data session
- **Industry-standard Fix** - Tag-value Fix 5.0 SP2 application layer over Fix 5 session
- **Full order lifecycle** - New, replace, cancel, mass cancel, mass cancel report, and execution report messages
- **ElectronX symbology** - Distinct symbol formats for Bounded Futures and Binary Options
- **Session safeguards** - Cancel-on-Disconnect and Cancel-on-Logout reduce stale order risk
- **Mass Quote Protection** - Per-bucket rolling-window execution cap with automatic order cancellation
- **Sequence recovery** - Standard Fix resend request, gap fill, and sequence reset
- **NLS branding** - Marketed as the Native Limit System order entry interface

