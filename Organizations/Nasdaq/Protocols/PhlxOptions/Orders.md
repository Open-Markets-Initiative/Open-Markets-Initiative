## PhlxOptions Orders: Nasdaq Phlx Options Order Entry

Ouch binary order entry protocol for submitting and managing options orders on the Nasdaq Phlx exchange.

### Overview

Orders provides the Ouch order entry interface to the Nasdaq Phlx matching engine for options trading. The protocol supports the complete order lifecycle including new order submission, replacement, cancellation, and execution reporting with immediate acknowledgment.

The protocol uses compact binary encoding with single-byte message type identifiers and fixed-length fields, delivered over SoupBinTcp session connections. The interface supports options-specific fields including series identification, order capacity, and options order types.

### Transport

SoupBinTcp session over Tcp.

### Key Characteristics

- **Options order entry** - Full order lifecycle for Phlx options trading
- **Low latency** - Optimized binary encoding for high-frequency order flow
- **Ouch protocol** - Compact fixed-length fields with single-byte message types
- **Immediate acknowledgment** - Order acceptance and rejection responses
