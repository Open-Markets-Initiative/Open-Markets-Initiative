## A2XEquities Trading Protocol: A2X Markets binary order entry (ATP)

Binary order entry protocol (Atp) for low-latency order submission and trading on A2X Markets, implemented on Aquis Exchange software.

### Overview

The A2X Binary Protocol is the Aquis Trading Protocol (ATP) as run by A2X Markets, a South African stock exchange that uses software provided by Aquis Exchange. It gives trading Members efficient, fixed-length binary messages aligned to the trading system's internal message structure for entering, modifying and cancelling orders and receiving responses and trades.

Session messages (login, logout, heartbeat) are unsequenced; business messages are sequenced in two streams, Member to A2X and A2X to Member, each starting at 1 each trading day, so missed messages can be resent when a Member logs in again. Version 3.0 moves A2X to the Aquis MTF software with ATP v2.11 on the wire, adding MiFID II flags and short codes and restricted orders.

### Transport

Tcp for login-authenticated member sessions carrying sequenced order entry, order management, trade capture and execution messages, with missed messages resent on login after a break.

### Key Characteristics

- **Aquis Trading Protocol** - Aquis ATP framing and message layouts as run by A2X Markets
- **Full order lifecycle** - Order add, modify, cancel, responses, trades and trade busts
- **Trade capture** - Large in Scale, Negotiated Benchmark Cross and Matched Principal trade reporting
- **Cancel on disconnect** - Open orders are cancelled when a session disconnects or logs out
- **Sequence numbered** - Bidirectional business message sequence numbers for recovery after a break

