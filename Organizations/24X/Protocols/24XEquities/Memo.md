## 24XEquities Memo: 24X Sbe Order Entry

Binary order entry protocol used by members to submit orders to the 24X National Securities Exchange over an Sbe-encoded subset of Fix 5.0 SP2.

### Overview

Memo is the binary order entry protocol for the 24X National Securities Exchange, providing members with a low-latency interface to submit, modify, and cancel orders for equities traded on 24X. The wire format is a sequenced messaging protocol using fixed width binary messages encoded as a subset of Fix 5.0 SP2 tags and messages via Simple Binary Encoding.

Messages are transported over the Memx-Tcp streaming channel which provides reliable ordered delivery between clients and servers. Memo carries the complete order lifecycle including new order submission, modification, cancellation, execution reports, fills, and rejects, using a Fix-compatible message model that is convenient for participants already familiar with the Fix protocol.

### Transport

Tcp via the Memx-Tcp streaming channel for reliable ordered delivery of order entry, modification, cancellation, and execution report messages between the client and the exchange.

### Key Characteristics

- **Sbe encoded** - Simple Binary Encoding for fixed-width low-latency parsing
- **Fix 5.0 SP2 subset** - Uses Fix standard tags and messages over a binary wire format
- **Memx-Tcp streaming** - Reliable ordered delivery between clients and servers
- **Full order lifecycle** - New, replace, cancel, execution report, fill, and reject messages
- **Member authenticated** - Persistent authenticated Tcp sessions per member
- **Extended hours** - Designed for 24X extended trading sessions

