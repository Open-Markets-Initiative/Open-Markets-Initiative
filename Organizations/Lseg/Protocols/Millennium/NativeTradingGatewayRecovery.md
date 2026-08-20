## Millennium Native Trading Gateway Recovery: Native Trading Gateway Recovery

Recovery channel of the Native Trading Gateway on the Lseg Millennium Exchange platform, replaying order and quote messages missed while disconnected from the Real Time Channel.

### Overview

The Recovery Channel is the second of the two channels that make up the Native Trading Gateway, documented as MIT203 section 6. A client that has been disconnected reconnects, logs in, and issues a Missed Message Request naming a partition and the last sequence number it received; the server acknowledges with a Missed Message Request Ack, transmits the missed messages, and closes the exchange with a Missed Message Report.

A recovery session may only be established after a Real Time session exists, using the same user name and password. Any attempt to connect to the Recovery Channel first is rejected with a reject code in the Logon Reply, and any New Password sent on this channel is ignored.

Three message types are unique to this channel: Missed Message Request, Missed Message Request Ack and Missed Message Report. Everything else it carries is shared with the Real Time Channel, so this specification composes the Real Time message set rather than restating it. Order Cancel Reject and Business Reject are never replayed, since neither is retained in the Order Cache.

### Transport

Bidirectional Tcp session on a port separate from the Real Time Channel, sharing the four byte Native message header and the Real Time Channel message layouts.

### Key Characteristics

- **Separate endpoint** - Its own Tcp port on each gateway instance, distinct from the Real Time Channel
- **Requires a Real Time session** - Logon is rejected unless a Real Time session has already been established
- **Request driven replay** - Messages are replayed in response to a Missed Message Request rather than streamed
- **Partitioned recovery** - A separate request is required per matching partition, identified by App ID
- **Shared wire format** - Identical framing, message type codes and message layouts to the Real Time Channel

