## Sail: Sola Access Information Language

Proprietary protocol developed by Tmx Group for order entry on the Montreal Exchange (Mx) Sola trading platform.

### Overview

Sail (Sola Access Information Language) is the native order entry protocol for the Sola trading platform powering derivatives trading at the Montreal Exchange. It provides direct access to the Sola matching engine for order submission, modification, cancellation, and mass cancellation of options and futures contracts.

The protocol supports the full order lifecycle including new order entry, modification, cancellation, and execution reporting. Sail includes a business design guide defining the trading workflows and a specifications guide defining the message formats and field layouts.

### Transport

Tcp to the Sola matching engine. The protocol includes built-in login, heartbeat, and sequencing mechanisms for session management.

### Key Characteristics

- **Derivatives order entry** - Purpose-built for Mx options and futures order management
- **Bidirectional** - Supports inbound order instructions and outbound execution reports
- **Sola platform native** - Designed specifically for the Sola matching engine
- **Session management** - Built-in login, heartbeat, and sequencing
- **Mass cancellation** - Cancel multiple orders matching specified criteria
