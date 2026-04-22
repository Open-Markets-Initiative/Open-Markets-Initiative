## Ouch: Order Update for Communication and Handling

Nasdaq Ouch order entry protocol a lightweight binary wire format for submitting, modifying, and cancelling orders with low latency execution reports on Nasdaq and licensed exchanges.

### Overview

OUCH is a binary order entry protocol designed for high-performance order submission, modification, and cancellation. It provides a streamlined interface for market participants to interact with exchange matching engines with minimal latency. The protocol supports a small, focused set of message types covering order lifecycle operations and execution reports.

Originally developed by Nasdaq, OUCH has been licensed to exchanges worldwide including ASX, Japannext, and Currenex. It is typically carried over the SoupBinTCP session layer and paired with ITCH for market data on the same venues.

### Transport

OUCH operates over TCP using the SoupBinTCP session layer protocol, providing reliable ordered delivery of order messages between the trading participant and the exchange. The session layer handles login, heartbeat, sequencing, and message recovery.

### Key Characteristics

- **Bidirectional** - Supports both inbound orders from participants and outbound execution reports from the exchange
- **Binary encoding** - Fixed-length messages with compact binary field representation
- **Session management** - SoupBinTCP provides login, heartbeat, and sequencing for connection management
- **Low latency** - Minimal overhead designed for latency-sensitive trading environments
- **Simple message set** - Focused protocol with a small number of message types for clarity

