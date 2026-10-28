## Drop Copy: Drop Copy

Nse's drop copy service, published per segment as the Protocol for Drop Copy Service. It delivers a read only copy of a member's own order and trade activity on a real time basis over a Tcp connection, in two subscriptions a member chooses between: Trade only, which carries the trade confirmations, and Order and Trade, which adds the order confirmations and rejections. A member may replay from the start of the trading day, or from the last sequence number it received, by naming that sequence number in the subscription request.

### Overview

The service is read only in substance rather than in framing. The member's half of the conversation is confined to logging on and subscribing; every application message travels from the host.

The segments are published as separate documents on two different generations of the protocol. Futures and Options and Capital Market are at version 3, which splits the service across one gateway router and a connection per market partition, frames messages with a fourteen byte Message Header, and may Lz4 compress a packed buffer of them. Currency Derivatives and Commodity Derivatives are at versions 1.7 and 1.5, which have a single connection and the forty byte interactive Message Header, and are the direct interface encoding.

A subscription names the last sequence number the member holds and the host downloads only what follows it, so a member that drops a connection during market hours is directed to resume incrementally rather than download the day again. A gap in the sequence is recovered the same way; a duplicate is dropped by the member.

Trade confirmations carry a Segment field naming the business segment the trade belongs to, so a confirmation identifies its own market rather than relying on which document described the connection.

The appendix of each document closes by directing a member to drop any transaction code the document does not define, which makes the message set open ended: the host may send a code this specification has never described.

### Transport

Drop copy connection between the member system and the drop copy host end, carrying the member's sign on and subscription requests one way and the session responses and downloaded confirmations the other.

### Key Characteristics

- **Header addressed** - A message header prefaces every message and its Transaction Code selects the structure
- **Big endian** - Fixed width fields, big endian on the wire, as the whole Non-Neat Front End family is
- **Sequenced** - Every message carries a sequence number a member subscribes from, and every packet carries its own sequence number the member validates
- **Authenticated** - Each packet carries an Md5 digest or a Gcm authentication tag over its message data, and a mismatch disconnects the session

