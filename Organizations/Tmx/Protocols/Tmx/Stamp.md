## Stamp: Tmx Toronto Stock Exchange Tagged Order Entry

Tagged-value order entry protocol for submitting, modifying, and cancelling orders on the Tmx Toronto Stock Exchange and Tsx Venture Exchange.

### Overview

Stamp is the order entry protocol for the Tmx Toronto Stock Exchange (Tsx) and Tsx Venture Exchange cash equities markets. It is a tagged-value protocol that provides members with a text-based interface for submitting, modifying, and cancelling orders, with full execution report handling over authenticated Tcp sessions.

### Transport

Tcp for persistent authenticated Stamp sessions carrying tagged order entry, modification, cancellation, and execution report messages.

### Key Characteristics

- **Toronto Stock Exchange** - Cash equities order entry for Tsx and Tsxv
- **Tagged value** - Text-based message format with field tags
- **Session based** - Persistent authenticated Tcp session per member
- **Full order lifecycle** - New, modify, cancel, and execution report messages
- **Equities coverage** - Tsx and Tsx Venture Exchange listed securities

