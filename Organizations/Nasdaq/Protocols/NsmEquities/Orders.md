## NsmEquities Orders: Nasdaq Stock Market Order Entry

Ouch binary order entry protocol for submitting and managing equity orders on the Nasdaq Stock Market.

### Overview

Orders provides the Ouch order entry interface to the Nasdaq Stock Market matching engine for Nsm-listed and Upa securities. The protocol supports the complete order lifecycle including new order submission, replacement, cancellation, and execution reporting with immediate acknowledgment of accepted orders.

The protocol uses compact binary encoding with single-byte message type identifiers and fixed-length fields, delivered over SoupBinTcp session connections. Order types include limit, market, and pegged orders with various time-in-force and display options.

### Transport

SoupBinTcp session over Tcp.

### Key Characteristics

- **Full order lifecycle** - New, replace, cancel, fill, and reject messages
- **Low latency** - Optimized binary encoding for high-frequency order flow
- **Ouch protocol** - Compact fixed-length fields with single-byte message types
- **Immediate acknowledgment** - Order acceptance and rejection responses
