## Optiq Drop Copy Fix: Euronext Optiq Fix 5.0 Drop Copy Service

Fix 5.0 (SP2) drop copy service delivering near real-time copies of order and trade report messages produced by the Euronext Optiq matching engine, for risk management, back-office, and compliance use across cash and derivatives markets.

### Overview

The Optiq Drop Copy Fix service provides participants with near real-time copies of the order and trade activity produced by Optiq, presented as Fix 5.0 (Service Pack 2) messages on a dedicated drop copy connection. It is intended for risk management, back-office, and compliance teams that need an independent, read-only view of order acknowledgements, modifications, cancellations, and executions without consuming the primary order entry session.

A drop copy configuration grants access to one or more logical accesses for a single participant, or across several Optiq segments, so that a single connection can observe activity spanning multiple order entry sessions. The feed reuses the standard Optiq Fix message structures (ExecutionReport, OrderCancelReject, and TradeCaptureReportAck) and field semantics from the order entry gateway; the same service is also offered in the Sbe binary encoding as a separate protocol.

### Transport

Tcp for a dedicated authenticated drop copy session delivering execution reports, order cancel rejects, and trade capture report acknowledgements as Fix 5.0 outbound copies, scoped to the client's configured logical accesses across Optiq segments.

### Key Characteristics

- **Fix 5.0 SP2** - Standards-based tagged-value drop copy of Optiq order and trade activity
- **Near real-time copies** - Order and trade report messages mirrored as they are produced by the matching engine
- **Risk and compliance** - Independent read-only view for risk management, back-office, and compliance
- **Execution reports** - Acknowledgement, modification, cancellation, and fill copies via ExecutionReport
- **Trade capture** - Trade execution copies via TradeCaptureReportAck
- **Multi-access scope** - One connection spanning multiple logical accesses and Optiq segments
- **Dedicated session** - Separate authenticated drop copy connection independent of order entry
- **Cash and derivatives** - Copies of activity across Euronext Optiq asset classes
