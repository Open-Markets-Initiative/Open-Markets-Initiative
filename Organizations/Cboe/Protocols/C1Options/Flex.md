## C1Options Flex: Cboe Options Flex Order Entry

Cboe Binary Order Entry protocol for submitting Flex (flexible) options orders with custom terms on Cboe Options Exchange (C1).

### Overview

Flex is the order entry protocol for Flex (flexible) options on Cboe Options Exchange (C1). Flex options allow market participants to customise contract terms such as strike price, expiration date, and exercise style beyond the standard listed options series. The protocol provides the message types needed to define and submit orders against these custom contracts.

It is built on the Cboe Binary Order Entry (Boe) session layer with authentication, sequence tracking, and reliable recovery. Execution reports and order status messages follow the same Boe conventions as standard options order entry, so clients can share decoder and session infrastructure.

### Transport

Tcp via the Cboe Binary Order Entry (Boe) session layer for persistent authenticated order flow with sequence tracking, heartbeats, and reliable recovery.

### Key Characteristics

- **Flex options** - Custom contract terms beyond standard listed options
- **Cboe Boe** - Native Cboe Binary Order Entry protocol
- **Session based** - Persistent authenticated Tcp session per member
- **Full order lifecycle** - New, modify, cancel, and execution report messages
- **Customisable terms** - Strike, expiration, and exercise style flexibility

