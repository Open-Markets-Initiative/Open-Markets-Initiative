## Sail: Tmx Montreal Exchange Order Entry

Order entry protocol for submitting, modifying, and cancelling orders on the Tmx Montreal Exchange derivatives markets.

### Overview

Sail is the Sola Access Information Language, the order entry protocol for the Tmx Montreal Exchange (Mx) derivatives markets. It provides members with a text-based tagged-value interface for submitting orders against Mx options, futures, and other derivatives products, delivered over authenticated Tcp sessions.

### Transport

Tcp for persistent authenticated Sail sessions carrying order entry, modification, cancellation, and execution report messages for Montreal Exchange derivatives.

### Key Characteristics

- **Montreal Exchange** - Order entry for Tmx Mx derivatives markets
- **Sola Sail** - Nasdaq Sola platform order entry specification
- **Tagged value** - Text-based message format with field tags
- **Session based** - Persistent authenticated Tcp session per member
- **Full order lifecycle** - New, modify, cancel, and execution report messages

