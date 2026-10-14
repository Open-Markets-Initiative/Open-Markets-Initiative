## TaifexDerivatives Order Entry: Taifex Tcp Ip Tmp and Fix Messaging Specifications

Order entry interface of the Taiwan Futures Exchange, used by futures commission merchants to submit, decrease and reprice single and multi-leg futures and options orders, enter and cancel market maker quotes, request quotes and Flex product definitions, query trading session status, exchange bulletins and file requests, and receive order status and execution reports. The interface is published in two encodings over the same Tcp line: the native binary Taifex Message Protocol, whose order and execution report line also carries the Link Subsystem that establishes a session, and a Financial Information eXchange binding of the same order, quote and report flows.

### Overview

The Taifex Fix interface is a Fix binding of the Taifex Message Protocol order entry service. It carries the same order, quote and report flows that Tmp identifies as R01, R02, R03, R07, R08 and R09, so each Fix message in the specification is annotated with the Tmp transaction it corresponds to. Fields that Tmp defines but Fix does not are added as Taifex user defined tags in the 10000 range.

The specification defines every message against both Fix 4.4 and Fix 4.2. Under Fix 4.2 the fields that version lacks are carried as Taifex user defined tags formed by prefixing the Fix 4.4 tag with 44, and the messages that version lacks are carried as user defined MsgType values beginning with U. This definition follows the Fix 4.4 binding and its standard tags and MsgType values.

Taifex departs from standard Fix order handling in that no pending message is sent. Where Fix 4.2 and 4.4 would answer a new, cancel or replace request with Pending New, Pending Cancel or Pending Replace, Taifex processes the request and replies only with the final success or failure execution report.

### Transport

Tcp for reliable ordered delivery of order entry, quote, and execution report messages, with separate sessions for the futures and options markets in regular and after hours trading, addressed by TargetCompID under the Fix encoding and by the system type and the futures commission merchant and session identifiers of the common message header under Tmp.

### Key Characteristics

- **Futures and options order entry** - Single and multi-leg orders for the Taifex derivatives market
- **Dual Fix version binding** - Every message defined against both Fix 4.4 and Fix 4.2
- **Market maker quoting** - Quote, quote cancel and quote status messages for market makers
- **Flex product definition** - Security definition request and response for tailored contracts
- **Decrease only amendment** - Order quantity may be decreased but never increased
- **No pending reports** - Requests are answered only with a final success or failure report

