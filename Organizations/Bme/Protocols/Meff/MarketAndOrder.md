## Meff Market And Order: MEFF Market And Order

The combined channel of the MEFF derivatives environment, which section 1.2 states carries market information and order entry over one Tcp session, so a member reads the whole market and enters its own orders without opening a second connection. It is the largest of the specifications: the full depth market message set, the private order entry traffic in both directions, and the session level messages, fifty one of the document's fifty eight messages in the Derivatives environment. Section 5.2 marks every market message for this server, and section 6.1.1 marks the order entry messages for it too, with the Market and Order forms of the private execution messages in place of the Order entry forms.

### Overview

No message type is used by both directions, so the direction of a message is a fact of its type rather than something the specification has to declare. The client's messages carry a two byte length and a one byte type; the server's carry a four byte sequence number as the first field of the body, which is where the message tables put it.

Section 6.2 gives the scenarios the messages serve. An order is entered with a Simple new order, or with Client Data where the member states the attributes the order carries, and each is acknowledged by a Simple Order Status. A quote takes New Quote, Quote modification and Quote cancellation, and a Quote Status answers each. Mass cancellation takes one message and answers with a completion or a reject.

An execution reaches the member twice over. The Execution Private Information messages state the member's own side of a match, one message per leg and side, and the Trade, Trade Amendment or Cancellation Private Information messages state a trade that did not come from order matching, or the amendment or cancellation of one. This server carries the Market and Order forms of the execution messages, 0x13 and 0x15, where the order entry server carries 0x12 and 0x14.

Section 3.5 names the three identifiers a member works with: an OrderID the client assigns and reuses, a SecondaryOrderID the system assigns and keeps for the life of the order, and a TrdMatchID the system assigns to each match. A RequestID carries the member's own reference back on every response.

### Transport

A session opened with a Logon naming a username and a password, which the server answers with a Logon Response stating the heartbeat interval and the protocol version. Silence is filled with Heartbeats, which repeat the last sequence number rather than consuming one, and a Reject answers a message the session level will not accept.

### Key Characteristics

- **Both directions in one specification** - The three byte header is what every message carries, so client and server messages share one branch table
- **Client messages carry no sequence number** - Section 2.1 gives one only to a published message, and the tables bear it out
- **Little endian** - Section 3.4.1 states that all numeric values are sent as little endian encoded integers
- **Per environment message layouts** - One document serves three environments, each field marked with the environments that send it
- **Private information** - The executions and trades on this channel are the member's own, not the market's

