## B3Derivatives Binary Entry Point: B3 Sbe Order Entry

Sbe-encoded binary order entry protocol for submitting, modifying, and cancelling orders on the B3 equities and derivatives platform with Fixp session layer.

### Overview

BinaryEntryPoint (Bep) is the B3 native binary order entry protocol used by market participants to submit, replace, and cancel orders across the B3 equities and derivatives markets. The wire format uses Simple Binary Encoding (Sbe) for fixed-width high performance message delivery, and application-level messages cover the full order lifecycle including simple new order, simple modify order, execution reports, and cancel rejects.

The session layer is Fixp (Fix Performance Session Layer) which defines the Negotiate and Establish handshake for session creation, sequence number tracking for reliable delivery, and recovery messages for reconnection after a session drop. Bep supports self-trade prevention instructions, market maker protection reset, and execution restatement reasons for richer order management semantics.

### Transport

Tcp for persistent authenticated sessions using the Fix Performance Session Layer (Fixp) with Negotiate and Establish messages for session start and sequence numbered delivery of order entry messages.

### Key Characteristics

- **Sbe encoded** - Fix Simple Binary Encoding for fixed-width low-latency parsing
- **Fixp session layer** - Negotiate and Establish handshake with sequence number tracking
- **Full order lifecycle** - New, modify, cancel, execution report, and cancel reject messages
- **Self-trade prevention** - Per-order self-trade prevention instructions
- **Market maker protection** - Mm protection reset support for market makers
- **Session recovery** - Reconnection support after catastrophic client failure
- **Equities and derivatives** - Unified order entry across B3 asset classes

