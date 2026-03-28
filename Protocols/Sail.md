## SAIL: Sola Access Information Language

Proprietary binary protocol with text elements developed by TMX Group and licensed to several exchanges for order entry on the Sola trading platform.

### Overview

SAIL (Sola Access Information Language) is the native order entry protocol for the Sola trading platform, which powers derivatives trading at the Montreal Exchange (MX) and other TMX Group venues. It provides direct access to the matching engine for order submission, modification, and cancellation of options and futures contracts.

The protocol supports the full order lifecycle including new order entry, modification, cancellation, mass cancellation, and execution reporting. SAIL is designed specifically for the Sola matching engine architecture and uses a hybrid encoding that combines binary framing with text-based field representation.

### Transport

SAIL operates over TCP, providing reliable ordered delivery of order messages between trading participants and the Sola matching engine. The protocol includes built-in login, heartbeat, and sequencing mechanisms for session management.

### Key Characteristics

- **Derivatives order entry** - Purpose-built for options and futures order management
- **Bidirectional** - Supports inbound order instructions and outbound execution reports
- **Hybrid encoding** - Combines binary framing with text-based field representation
- **Sola platform native** - Designed specifically for the Sola matching engine architecture
- **Session management** - Built-in login, heartbeat, and sequencing mechanisms
