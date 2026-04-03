## IseOptions Otto: Nasdaq Ise Options Order Entry

Ouch-based binary order entry protocol for submitting and managing options orders on the Nasdaq Ise exchange.

### Overview

Otto provides the Ouch order entry interface to the Nasdaq Ise matching engine for options trading. The protocol extends the standard Ouch framework with options-specific fields including series identification, order capacity, and options-specific order types and time-in-force values.

The protocol supports the complete order lifecycle including new order submission, replacement, cancellation, and execution reporting over SoupBinTcp session connections. Otto handles both simple single-leg orders and complex multi-leg strategy orders.

### Transport

SoupBinTcp session over Tcp.

### Key Characteristics

- **Options order entry** - Full order lifecycle for Ise options trading
- **Complex order support** - Multi-leg strategy order submission
- **Ouch-based protocol** - Compact binary encoding with single-byte message types
- **Immediate acknowledgment** - Order acceptance and rejection responses
