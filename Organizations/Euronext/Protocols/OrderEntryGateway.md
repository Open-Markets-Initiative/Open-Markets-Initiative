## Order Entry Gateway: Euronext Optiq Sbe Order Entry

Sbe-encoded binary order entry gateway for the Euronext Optiq trading platform supporting order, quote, and mass action submission across cash and derivatives markets.

### Overview

The Optiq Order Entry Gateway (Oeg) is the primary order entry channel for Euronext participants connecting to the Optiq trading platform. It supports the full order lifecycle across Euronext cash equities, fixed income, and derivatives markets, including new order entry, order modification, cancellation, mass cancellation, and mass quote submission for market makers.

The wire format uses Fix Simple Binary Encoding (Sbe) for compact fixed-width messages that decode with minimal overhead. Sessions are authenticated at logon, sequence numbers are tracked bidirectionally, and the gateway provides replay of unacknowledged messages on reconnection. Execution reports and drop-copy events are delivered on the same session as outbound orders, giving clients a complete view of their order activity.

### Transport

Tcp for persistent authenticated Optiq sessions carrying order submission, modification, cancellation, mass quote, and execution report messages with sequence-numbered reliable delivery.

### Key Characteristics

- **Optiq platform** - Native order entry gateway for the Euronext Optiq trading system
- **Sbe encoded** - Fix Simple Binary Encoding for fixed-width low-latency parsing
- **Full order lifecycle** - New, modify, cancel, mass cancel, and execution report messages
- **Mass quoting** - Market maker mass quote submission in a single message
- **Session based** - Authenticated Tcp session with bidirectional sequence tracking
- **Reliable delivery** - Retransmission of unacknowledged messages on reconnection
- **Cash and derivatives** - Unified order entry across Euronext Optiq asset classes

