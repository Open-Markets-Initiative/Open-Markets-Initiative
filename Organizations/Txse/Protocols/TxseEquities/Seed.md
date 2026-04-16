## TxseEquities Seed: Txse Binary Order Entry

Binary order entry protocol used by members to submit orders to the Texas Stock Exchange using the Rake session and framing layer.

### Overview

Seed is the order entry protocol for the Texas Stock Exchange (Txse), providing members with a binary interface to submit, modify, and cancel orders for equities listed on the Txse venue. The wire format is a sequenced fixed-width binary protocol delivered over the Txse Rake session and framing layer.

The Rake layer provides session authentication, sequence number tracking, heartbeat monitoring, and gap recovery, which lets Seed focus on application-level order lifecycle messages. Inbound messages cover new order submission, order replacement, cancellation, and order status queries, and outbound messages report order accepted, replaced, cancelled, executed, and rejected events back to the client.

### Transport

Tcp via the Txse Rake session layer for persistent authenticated order entry sessions carrying order submission, modification, cancellation, and execution report messages.

### Key Characteristics

- **Binary order entry** - Compact fixed-width messages for low-latency processing
- **Rake layer** - Runs on top of the Txse session and framing transport
- **Full order lifecycle** - New, replace, cancel, execution report, and reject messages
- **Session based** - Authenticated Tcp session per member via Rake
- **Sequence numbered** - Reliable ordered delivery with gap detection
- **Equities order entry** - Designed for the Texas Stock Exchange equities venue

