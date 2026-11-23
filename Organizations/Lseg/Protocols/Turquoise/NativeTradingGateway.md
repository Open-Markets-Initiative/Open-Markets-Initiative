## Turquoise Native Trading Gateway: Native Trading Gateway

Native Trading Gateway order entry interface of Turquoise, documented as TQ301, carrying order submission, amendment, cancellation and mass cancellation, BTF pre-arranged trades and their execution reports over a bidirectional Tcp session.

### Overview

Participants submit new orders, cancel/replaces, cancels and mass cancels to the Turquoise Lit, Turquoise Dark and Turquoise Periodic Auctions order books, selected per order by Target Book, and receive execution reports covering acceptance, rejection, execution, expiry, cancellation, restatement, BI triggering and pending cancel. BTF pre-arranged trades are submitted with New Cross/BTF and cancelled with Cross/BTF Cancel Request.

Server messages are sequenced per matching partition: Execution Report, Order Cancel Reject, Order Mass Cancel Report and Business Reject carry the partition's App ID and a Sequence No, which a Participant quotes in a Missed Message Request on the Recovery Channel.

Prices are eight byte signed integers with eight implied decimal places. Expire Date Time is Unix seconds in UTC, and Transact Time carries Unix seconds in its first four bytes and nanoseconds in the next four, in UTC.

### Transport

Bidirectional Tcp session between the Participant and the gateway, framed by a four byte message header. The Participant must send a Logon within one heartbeat interval of connecting, and messages missed while disconnected are recovered through the separate Recovery Channel.

### Key Characteristics

- **Native binary** - Fixed width little endian binary messages rather than Fix tags
- **Three order books** - Lit, Dark and Periodic Auctions books selected per order by Target Book
- **BTF pre-arranged trades** - Internal and Committed BTF trades submitted and cancelled with their own messages
- **Partitioned sequencing** - Server messages are numbered per matching partition for recovery

