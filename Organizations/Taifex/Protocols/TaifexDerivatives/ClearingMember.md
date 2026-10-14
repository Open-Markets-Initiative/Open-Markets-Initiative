## TaifexDerivatives Clearing Member: Taifex Tcp Ip Tmp Messaging Specifications

Clearing member order and execution report line of the Taiwan Futures Exchange, over which a clearing member receives the orders and executions of the downline futures commission merchants it settles for, in both the regular and the FLEX trading systems. A clearing member subscribes to one of three data sets per connection through an initiate operation message: the downline firm order and execution report, the downline firm execution report, or the execution report including head office and branch offices. The line carries reports only and no order input.

### Overview

The line is not a trading line. Section 2.5.5 states it does not provide the trading related functions, naming the trade session status request and report, the bulletin request and report and their FLEX counterparts, and section 2.5.4 that Taifex provides no resend by way of the resend report message and its confirmation.

The reports reuse the order line's formats. Sections 2.5.5.3 to 2.5.5.5 state that the clearing member order status report, the quote status report and the execution report all use the order status report format, differing only in the target identifier and in carrying fewer sets of data, and the execution report including head office and branch offices is the order line's own R06.

Every message of the line carries a message sequence number of 0, and the report sequence number of the report itself is used in its place to detect a gap. A clearing member may run one connection per data set: one for the downline firm order and execution report and another for the execution report including head office and branch offices.

FLEX reports are subscribed to separately. After the session is activated the clearing member sends a FLEX initiate operation message per partition and Taifex confirms it, after which the FLEX order status reports of that partition follow.

### Transport

Tcp session addressed by the futures commission merchant and session identifiers of the common message header, joined by entering 8 in the application system code of the request logon. The Link Subsystem establishes the session as on the order line, except that Taifex provides no resend of data and the clearing member enters 0 for the requested start sequence.

### Key Characteristics

- **Reports only** - The line carries no order input, price inquiry or quote input
- **Subscribed per connection** - An initiate operation message names which of the three data sets the connection receives
- **No resend** - The resend report message and its confirmation are not provided on this line
- **Regular and Flex** - Regular reports are subscribed through R15 and Flex reports per partition through RX15
- **Report sequenced** - A gap is detected from the report sequence number, the message sequence number being 0 throughout

