## Orders Api: Coinbase Derivatives Sbe Order Entry

Sbe-encoded binary order entry api used by Lead Market Makers to submit, modify, and cancel orders on Coinbase Derivatives with 30 to 80 microsecond round trip quoting.

### Overview

The Coinbase Derivatives orders api is the binary order entry protocol used by Lead Market Makers to connect to Coinbase Derivatives. It is built on Simple Binary Encoding (Sbe) and allows connected firms to send, modify, and cancel their orders in a simplified and efficient manner, with expected latency of 30 to 80 microseconds roundtrip for quoting workflows.

The protocol defines a session layer for authentication and sequence number tracking along with application-level messages for new order submission, order replacement, cancellation, and execution reporting. The simplified message set is tuned specifically for the quoting use case where market makers continuously refresh two-sided prices across many instruments.

### Transport

Tcp for persistent authenticated sessions carrying order entry, modification, cancellation, and execution report messages between connected firms and Coinbase Derivatives.

### Key Characteristics

- **Sbe encoded** - Simple Binary Encoding for fixed-width low-latency parsing
- **Low latency** - 30 to 80 microsecond roundtrip expected for quoting workloads
- **Market maker tuned** - Message set optimized for continuous two-sided quoting
- **Full order lifecycle** - New, modify, cancel, and execution report messages
- **Session based** - Authenticated Tcp session with sequence number tracking
- **Lead Market Maker** - Primary interface for Coinbase Derivatives liquidity providers

