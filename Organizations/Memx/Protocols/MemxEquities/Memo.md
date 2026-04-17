## MemxEquities Memo: Memx Sbe Order Entry

Binary order entry protocol used by members to submit orders to the Members Exchange equities and options markets over an Sbe-encoded subset of Fix 5.0 SP2.

### Overview

Memo is the Memx order entry protocol for trading equities and options on the Members Exchange (Memx). The wire format is a sequenced messaging protocol using fixed width binary messages encoded as a subset of Fix 5.0 SP2 tags and messages via Simple Binary Encoding, providing members with a low-latency interface for submitting, modifying, and cancelling orders across both asset classes.

Messages are transported over the Memx-Tcp streaming channel which provides reliable ordered delivery between clients and servers. Memo carries the complete order lifecycle including new order submission, modification, cancellation, execution reports, fills, and rejects, with risk checks applied inline during order processing before the order reaches the matching engine.

### Transport

Tcp via the Memx-Tcp streaming channel for reliable ordered delivery of order entry, modification, cancellation, and execution report messages between the client and the exchange.

### Key Characteristics

- **Sbe encoded** - Simple Binary Encoding for fixed-width low-latency parsing
- **Fix 5.0 SP2 subset** - Uses Fix standard tags and messages over a binary wire format
- **Memx-Tcp streaming** - Reliable ordered delivery between clients and servers
- **Full order lifecycle** - New, replace, cancel, execution report, fill, and reject messages
- **Equities and options** - Unified order entry across Memx asset classes
- **Inline risk checks** - Pre-trade risk validation applied during order processing

