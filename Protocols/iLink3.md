## iLink3: Cme Globex Sbe Order Entry

Sbe-encoded binary order entry protocol for submitting, modifying, and cancelling orders on the Cme Globex electronic trading platform with Fixp session layer.

iLink 3 is Cme's current-generation Sbe-based binary order entry protocol, succeeding iLink 2 and unifying order entry across the Cme Globex complex.

### Overview

iLink 3 is the binary order entry protocol for the Cme Globex electronic trading platform, providing members with a low-latency interface to submit, modify, and cancel orders for futures and options across the Cme complex. The wire format uses Fix Simple Binary Encoding (Sbe) and runs over the Fix Performance Session Layer (Fixp) for session authentication and sequence tracking.

The protocol covers the full order lifecycle including new order single, order cancel replace, order cancel, order mass action, execution reports, and business message rejects. Fixp provides the Negotiate and Establish handshake for session creation, sequence number tracking for reliable delivery, and session recovery after reconnection.

### Transport

Tcp via the Fix Performance Session Layer (Fixp) for persistent authenticated sessions carrying order entry, modification, cancellation, mass action, and execution report messages.

### Key Characteristics

- **Cme Globex** - Order entry across the Cme complex
- **Sbe encoded** - Fix Simple Binary Encoding for fixed-width low latency
- **Fixp session layer** - Negotiate and Establish with sequence tracking
- **Full order lifecycle** - Order, modify, cancel, mass action, and execution report messages
- **Session recovery** - Retransmission of unacknowledged messages after reconnection
- **Futures and options** - Unified order entry across Cme asset classes

