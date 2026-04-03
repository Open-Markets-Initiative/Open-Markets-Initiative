## Fix: Aquis Fix Order Entry

Fix protocol implementation for submitting and managing orders on the Aquis Exchange.

### Overview

Fix is the Financial Information Exchange protocol implementation provided by Aquis Exchange for order entry and trade management. It offers a widely adopted, tag-value-based messaging interface for firms that prefer standard Fix connectivity over the native binary Atp protocol.

The Aquis Fix gateway supports standard order entry operations including new orders, modifications, cancellations, and execution reports using Fix session and application layer semantics. The implementation provides a familiar integration path for trading firms already connected to other venues via Fix.

### Transport

Tcp to Aquis Fix gateways. Fix sessions are established using standard Fix logon handshake with sequence number synchronization and heartbeat monitoring.

### Key Characteristics

- **Fix tag-value format** - Standard Fix message encoding for broad compatibility
- **Full order lifecycle** - New order, modify, cancel, and execution report messages
- **Session layer** - Fix session protocol with logon, heartbeat, and sequencing
- **Standard integration** - Familiar Fix interface for multi-venue trading platforms
- **Multiple order types** - Limit, market, and pegged order support
