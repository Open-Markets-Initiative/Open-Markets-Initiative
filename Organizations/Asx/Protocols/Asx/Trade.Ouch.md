## Trade.Ouch: Asx Trade Equities Ouch Order Entry

Binary order entry protocol for submitting, replacing, and cancelling orders on the Asx Trade cash equities platform.

### Overview

Asx Trade Ouch is the binary order entry protocol for the Asx Trade cash equities platform, providing members with a low-latency session-based interface to submit, modify, and cancel orders. The wire format uses the Ouch message family with fixed-width binary fields and numeric references for efficient processing on both sides of the connection.

The protocol defines inbound messages for entering new orders, replacing existing orders, cancelling by the client-assigned token, and cancelling by order identifier. Outbound messages report order accepted, rejected, cancelled, replaced, and executed events, giving clients a complete view of the order lifecycle over the trading session.

### Transport

Tcp for persistent authenticated trading sessions, carrying inbound Enter Order, Replace Order, Cancel Order and Cancel By Order Id messages and outbound execution reports and acknowledgements.

### Key Characteristics

- **Session-based** - Persistent Tcp session per member for order entry
- **Enter Order** - New order submission with full order parameters
- **Replace Order** - In-place modification of an existing order
- **Cancel Order** - Cancellation by client token or by order identifier
- **Execution reports** - Order accepted, cancelled, replaced, and executed messages
- **Binary encoded** - Compact fixed-width Ouch-style messages for low latency processing
- **Equities order entry** - Designed for Asx Trade cash equities

