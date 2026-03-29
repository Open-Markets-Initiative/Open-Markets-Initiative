## Stamp: Tmx Stamp Order Entry

Tmx Group's order entry protocol for submitting and managing orders on Tsx, Tsxv, and Tsx Alpha Exchange.

### Overview

Stamp is the Tmx Group's order entry protocol providing direct access to the Tsx, Tsxv, and Tsx Alpha Exchange matching engines for equity order submission, modification, and cancellation. The protocol supports the full order lifecycle for Canadian equity trading including new orders, modifications, cancellations, and execution reporting.

Stamp uses a binary message format designed for reliable order delivery over Tcp connections with built-in session management including login, heartbeat, and sequencing.

### Transport

Tcp with built-in session management. Persistent connections between trading participants and the Tmx matching engine gateways.

### Key Characteristics

- **Equities order entry** - Purpose-built for Tsx, Tsxv, and Tsx Alpha Exchange
- **Binary encoding** - Compact binary message format
- **Bidirectional** - Supports inbound orders and outbound execution reports
- **Session management** - Built-in login, heartbeat, and sequencing
- **Multi-exchange** - Single protocol across Tsx, Tsxv, and Alpha
