## PearlEquities Express Orders: Miax Pearl Equities Low Latency Order Entry

Low-latency binary order entry protocol for submitting, modifying, and cancelling orders on the Miax Pearl Equities Exchange.

### Overview

Miax Pearl Equities Express Orders (Meo) is the low-latency binary order entry protocol for the Miax Pearl Equities Exchange. It provides members with a high-performance native interface to submit, modify, and cancel orders for Nms securities listed on the Pearl Equities venue, using the Miax Express binary message format shared across the Miax family of protocols.

The protocol runs over Tcp with the Miax Express Session Manager (ESesM) providing session authentication, heartbeat monitoring, and sequence-based recovery. Application messages cover the full order lifecycle including new order submission, replace, cancel, execution reports, cancel rejects, and trading status updates from the matching engine back to the client.

### Transport

Tcp for persistent authenticated Miax Express order entry sessions using the ESesM session layer, carrying order, modification, cancellation, and execution report messages.

### Key Characteristics

- **Low latency** - Miax Express binary order entry path
- **Miax Express** - Native binary message format for the Miax platform
- **ESesM session** - Session layer for authentication and sequence recovery
- **Full order lifecycle** - New, replace, cancel, execution report, and cancel reject messages
- **Nms equities** - Order entry for Miax Pearl Equities listed securities
- **Tcp delivered** - Persistent authenticated session per member

