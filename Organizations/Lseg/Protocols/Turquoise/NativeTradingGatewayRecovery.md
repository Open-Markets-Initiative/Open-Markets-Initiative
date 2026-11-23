## Turquoise Native Trading Gateway Recovery: Native Trading Gateway Recovery

Recovery Channel of the Turquoise Native Trading Gateway, replaying the sequenced server messages a Participant missed while disconnected from the Real Time Channel.

### Overview

A Participant first establishes a Real Time Channel session, then logs on to the Recovery Channel with the same CompID and password; a Recovery Channel logon without one is rejected in the Logon Reply. It sends one Missed Message Request per partition, naming the App ID and the last Sequence No received; the server answers with a Missed Message Request Ack, transmits the missed messages and closes with a Missed Message Report.

The number of requests per day and of messages per request are limited. If the Order Cache fails over, the gateway sends a System Status naming the partition whose recovery service is unavailable, and another when it resumes. After a Missed Message Report or Ack the server waits five heartbeat intervals before disconnecting.

### Transport

Bidirectional Tcp session on its own address and port, sharing the four byte Native message header and the Real Time Channel message layouts.

### Key Characteristics

- **Requires a Real Time session** - Logon is rejected unless a Real Time session has already been established
- **Request driven replay** - Messages are replayed in response to a Missed Message Request rather than streamed
- **Partitioned recovery** - A separate request is required per matching partition, identified by App ID

