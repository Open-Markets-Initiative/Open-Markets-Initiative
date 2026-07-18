## AquisEquities Trading Protocol: Aquis Exchange order entry

Proprietary binary order entry protocol (Atp) for efficient low-latency order submission and trading on Aquis Exchange.

### Overview

Atp is the proprietary binary trading protocol developed by Aquis Exchange to provide efficient, streamlined, and low-latency order entry. It is the native interface for trading members submitting orders, modifications, and cancellations for equities listed on the Aquis platform.

The protocol supports a rich set of trading features including order references, clearing configuration, cancel on disconnect, self-trade prevention, post-only orders and post-only cancel-replace variants, Market at Close handling, and order sweeps. Execution reports and order status updates are delivered on the same Tcp session that carries outbound orders.

### Transport

Tcp for persistent authenticated member sessions carrying order submission, modification, cancellation, and execution report messages with sequenced streaming delivery.

### Key Characteristics

- **Proprietary binary** - Custom low-latency wire format native to Aquis Exchange
- **Full order lifecycle** - New, modify, cancel, execution report, and reject messages
- **Cancel on disconnect** - Automatic order cancellation if the session drops
- **Self-trade prevention** - Built-in protection against self-matching
- **Post-only orders** - Non-aggressing order types with cancel-replace variants
- **Market at Close** - Support for closing auction order types
- **Order sweeps** - Grouped order actions for fast risk management
- **Sequence numbered** - Bidirectional sequence numbers for reliable session recovery

