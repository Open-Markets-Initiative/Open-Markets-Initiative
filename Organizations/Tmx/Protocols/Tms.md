## Tms: Sola Trade Management System

Tmx Group's trade management protocol for the Montreal Exchange (Mx) Sola trading platform.

### Overview

The Sola Trade Management System (Tms) provides post-trade functionality for the Montreal Exchange derivatives market. Tms supports trade management operations including trade inquiry, trade cancellation, trade adjustment, and give-up/take-up processing for options and futures traded on the Sola platform.

The protocol enables clearing members and trading participants to manage their executed trades, process allocations, and handle trade lifecycle events through the Sola infrastructure.

### Transport

Tcp connection to the Sola platform. Session-based connectivity with authentication and trade management messaging.

### Key Characteristics

- **Post-trade focused** - Trade management and clearing operations for Mx derivatives
- **Sola platform** - Native integration with the Sola matching engine
- **Trade lifecycle** - Inquiry, cancellation, adjustment, and give-up/take-up processing
- **Clearing integration** - Support for clearing member operations
