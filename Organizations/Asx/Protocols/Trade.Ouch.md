## Trade Ouch: Asx Securities Order Entry

Trade Ouch order entry protocol for submitting and managing orders on the Asx Trade platform.

### Overview

Trade Ouch is the binary order entry protocol for the Asx Trade platform, providing a low-latency interface for submitting, modifying, and cancelling orders for exchange-traded options and futures. The protocol uses compact fixed-length messages designed for minimal encoding and decoding overhead.

The protocol carries new order instructions, replace and cancel requests, and execution reports including fill notifications and order status updates. Trade Ouch provides the full order lifecycle for direct market access participants and algorithmic trading systems connecting to the Asx Trade matching engine.

### Transport

Tcp to Asx Trade matching engine gateways with session authentication, heartbeat monitoring, and sequence number tracking.

### Key Characteristics

- **Binary order entry** - Compact fixed-length messages for low-latency order handling
- **Options and futures** - Order entry for Asx Trade platform derivatives
- **Full order lifecycle** - New order, replace, cancel, and execution report messages
- **Real-time execution reports** - Immediate acknowledgments and fill notifications
