## CoinbaseDeribit Orders Api: Coinbase Deribit Sbe Order Entry

Sbe-encoded binary order entry api used by market makers and direct trading firms to submit, modify, and cancel orders on Coinbase Deribit crypto derivatives.

### Overview

The Coinbase Deribit orders api is the binary order entry protocol used by market makers and direct trading firms to connect to Coinbase Deribit. It is built on Simple Binary Encoding (Sbe) and allows connected firms to send, modify, and cancel orders for crypto options and futures in a simplified and efficient manner tuned for low-latency quoting.

The protocol defines a session layer for authentication and sequence number tracking along with application-level messages for new order submission, order replacement, cancellation, and execution reporting. The simplified message set is tuned specifically for the quoting use case where market makers continuously refresh two-sided prices across many instruments.

### Transport

Tcp for persistent authenticated sessions carrying order entry, modification, cancellation, and execution report messages between connected firms and Coinbase Deribit.

### Key Characteristics

- **Crypto derivatives order entry** - Order submission, modification, and cancellation for Deribit options and futures
- **Sbe encoded** - Simple Binary Encoding for fixed-width low-latency parsing
- **Authenticated session** - Tcp session lifecycle with negotiate, establish, heartbeat, and terminate
- **Quoting workflow** - Message set tuned for continuous two-sided market making
- **Execution reporting** - Server-driven execution reports for fills, cancels, and rejects

