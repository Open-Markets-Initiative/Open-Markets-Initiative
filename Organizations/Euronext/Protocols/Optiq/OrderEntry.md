## Optiq Order Entry Fix: Euronext Optiq Fix 5.0 Order Entry

Fix 5.0 (SP2) order entry interface to the Euronext Optiq Order Entry Gateway, providing order, quote, mass action, wholesale, and request-for-quote messaging across Euronext cash and derivatives markets as a tagged-value alternative to the Sbe binary encoding.

### Overview

The Optiq Order Entry Fix interface is the Fix 5.0 (Service Pack 2) presentation of the Euronext Optiq Order Entry Gateway (Oeg), giving participants a standards-based tagged-value channel for the full order lifecycle across Euronext cash equities, fixed income, and derivatives markets. It carries new order entry, modification, cancellation, mass cancellation, mass quoting for market makers, request for quote, wholesale and cross orders, and the corresponding execution reports and acknowledgements.

Sessions are established with a Logon (A) carrying the logical access, partition, and next expected sequence number; the gateway tracks sequence numbers bidirectionally and replays missed messages on reconnection without an explicit ResendRequest. The same session delivers execution reports and request acknowledgements, and the protocol exposes Euronext-specific functionality through custom tags and User-Defined message types (for example RFQ, wholesale, ERG risk, and clear-book operations) layered on the standard Fix 5.0 message set.

### Transport

Tcp for persistent authenticated Optiq order entry sessions carrying Fix 5.0 administrative and application messages with bidirectional sequence numbering, gap detection, and automatic retransmission of missed messages on reconnection.

### Key Characteristics

- **Fix 5.0 SP2** - Standards-based tagged-value order entry with DefaultApplVerID FIX50SP2
- **Optiq platform** - Fix presentation of the Euronext Optiq Order Entry Gateway
- **Full order lifecycle** - New, modify, cancel, mass cancel, and execution report messages
- **Mass quoting** - Market maker mass quote submission and acknowledgement
- **Request for quote** - Quote request, RFQ notification, and matching status messaging
- **Wholesale and cross** - Wholesale order, cross order, and implied execution requests
- **Session based** - Authenticated Tcp session with bidirectional sequence tracking and gap recovery
- **Cancel on disconnect** - Optional automatic cancellation of orders when the session drops
- **Cash and derivatives** - Unified order entry across Euronext Optiq asset classes
