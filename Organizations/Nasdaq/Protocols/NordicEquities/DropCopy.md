## NordicEquities Drop Copy: Nasdaq Nordic Fix Drop

Fix drop copy for the Nasdaq Nordic equities markets running on the Inet Nordic platform, delivering a read only copy of order and execution activity entered over Ouch or Fix.

### Overview

The Nordic Fix drop copies the order lifecycle of a firm's Ouch and Fix order entry sessions onto a separate read only Fix session. Every accepted, replaced, restated, executed, broken and cancelled order is relayed as a Fix 5.0 SP2 Execution Report, and rejected cancel or replace requests as an Order Cancel Reject.

Execution reports carry the MiFid II short codes for client, investment decision maker and execution decision maker in the party group, the MMT trade flags, execution algo parent and child linkage, and the self trade prevention and internalisation flags. The PureStream line adds the PureStream indication of interest fields.

### Transport

Tcp session framed by the Nasdaq Nordic Fixt 1.1 transport layer on a dedicated Fix drop connection, with sequence number recovery through Resend Request and Sequence Reset.

### Key Characteristics

- **Drop copy** - Read only copy of Ouch and Fix order activity
- **Fix 5.0 SP2** - Application messages over a Fixt 1.1 session
- **MiFid II** - Short code parties and MMT trade flags
- **Session based** - Persistent authenticated Tcp Fix session

