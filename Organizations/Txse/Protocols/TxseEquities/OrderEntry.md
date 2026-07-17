## TxseEquities Order Entry: TXSE FIX 5.0 SP2 order entry and drop copy

FIX 5.0 SP2 order entry interface for the Texas Stock Exchange. Members submit New Order Single, Order Cancel/Replace Request, and Order Cancel Request messages and receive Execution Reports covering acknowledgment, reject, trade, replace, cancel, restatement, and trade cancel/correct events. The interface also serves drop copy sessions, and TXSE extends the protocol with custom fields (LocateBroker 5700, PriceSlideInstruction 9402) and custom enumeration values.

### Overview

TXSE FIX Order Entry is the FIX 5.0 SP2 interface for submitting orders to the Texas Stock Exchange. The inbound vocabulary is the standard order lifecycle - New Order Single, Order Cancel/Replace Request, Order Cancel Request - and the outbound Execution Report carries variant layouts discriminated by ExecType: new order acknowledgment, order rejected, trade, order replaced, order canceled or expired, restatement, and trade cancel/correct.

The session layer is published as a companion FIX Session Layer Protocol document covering Logon, Logout, Heartbeat, Test Request, Reject, Resend Request, and Sequence Reset. Orders support pegging (PegOffsetValue), reserve display quantity, minimum quantity, locate-required short selling with a custom LocateBroker field, and a custom PriceSlideInstruction.

### Transport

Persistent authenticated FIX session over Tcp with standard sequence-number recovery (Logon, Logout, Heartbeat, Test Request, Reject, Resend Request, Sequence Reset).

### Key Characteristics

- **Fix 5.0 SP2** - Standard tag-value order entry over an authenticated Tcp session
- **Full order lifecycle** - New Order Single, Cancel/Replace, Cancel, and Execution Report variants
- **ExecType variants** - Acknowledgment, reject, trade, replace, cancel, restatement, and trade cancel/correct execution reports
- **TXSE custom fields** - LocateBroker (5700) and PriceSlideInstruction (9402) extensions
- **Reserve and pegged orders** - DisplayQty reserve replenishment and PegOffsetValue basis-point pegging

