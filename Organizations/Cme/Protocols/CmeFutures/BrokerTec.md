## CmeFutures Broker Tec: Cme BrokerTec Fixed Income Order Entry

Binary order entry protocol for submitting orders on the Cme BrokerTec fixed income electronic trading venue.

### Overview

BrokerTec is the Cme fixed income electronic trading venue covering US Treasuries, European repos, and European government bonds. The BrokerTec order entry protocol provides members with a binary session-based interface to submit, modify, and cancel orders against the fixed income order book.

The protocol is distinct from the Cme Globex iLink 3 interface, reflecting the fixed income trading workflow and the specific order types available on the BrokerTec venue.

### Transport

Tcp for persistent authenticated BrokerTec sessions carrying order entry, modification, cancellation, and execution report messages for fixed income instruments.

### Key Characteristics

- **Fixed income** - US Treasuries, European repos, European government bonds
- **BrokerTec venue** - Cme fixed income electronic trading platform
- **Session based** - Persistent authenticated Tcp session per member
- **Full order lifecycle** - New, modify, cancel, and execution report messages
- **Binary encoded** - Compact fixed-width messages for low latency

