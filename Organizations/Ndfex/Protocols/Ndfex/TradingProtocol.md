## Trading Protocol: Ndfex Equities Order Entry

Binary order entry protocol for submitting, modifying, and cancelling orders on the Ndfex exchange.

### Overview

Ndfex Trading Protocol is the order entry interface for the Ndfex exchange, providing members with a binary session-based protocol for submitting and managing orders for listed equities.

### Transport

Tcp for persistent authenticated trading sessions carrying order entry, modification, cancellation, and execution report messages.

### Key Characteristics

- **Ndfex order entry** - Binary order submission for listed equities
- **Obp encoded** - Binary message encoding
- **Session based** - Persistent authenticated Tcp session
- **Full order lifecycle** - New, modify, cancel, and execution reports

