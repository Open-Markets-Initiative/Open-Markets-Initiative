## TaifexDerivatives Drop Copy: Taifex Tcp Ip Tmp Messaging Specifications

Drop copy service of the Taiwan Futures Exchange, the Tmpdc session, over which a futures commission merchant receives copies of its own orders, trades and error reports from the regular and the FLEX trading systems. Each drop copy session maps to a dedicated order session, whose identity the firm reads from the mapping file, and carries the copies of the orders that session placed over any protocol.

### Overview

The message format is that of the clearing member line. Section 2.10.4 states that the drop copy session's message format is the same as the clearing member order execution report, with the initiate operation messages carrying target identifier 7 for a reply in the order status report format and 17 for a reply in its long product format.

The line carries copies of every protocol. The service transfers the order reply data of the Tmp session and of both Fix sessions, so a firm placing orders over Fix reads their drop copies here in the Tmp encoding.

The report sequence number is redefined as the order session's own, rather than the drop copy session's, so a copy is tied back to the session that placed the order. Taifex does not send copies whose report sequence number is 0.

FLEX copies are subscribed to separately, per partition, through a FLEX initiate operation message with target identifier 7, after which the FLEX order status and error reports of the original order session follow for that partition.

### Transport

Tcp session whose address is resolved from the product group and connection port mapping file through the Taifex domain name system server, joined by entering 7 in the application system code of the request logon.

### Key Characteristics

- **Copies only** - The line carries no order input, and no message a firm sends other than the subscription
- **Mapped to one order session** - Each drop copy session maps to a dedicated order session named in the mapping file
- **Every protocol** - Copies cover orders placed over Tmp and over both Fix versions
- **Order session sequenced** - The report sequence number is the original order session's, not the drop copy session's
- **Regular and Flex** - Regular copies are subscribed through R15 and Flex copies per partition through RX15

