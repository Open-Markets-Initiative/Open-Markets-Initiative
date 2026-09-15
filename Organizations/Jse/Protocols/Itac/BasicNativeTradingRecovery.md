## Itac Basic Native Trading Recovery: Basic Native Trading Recovery

Recovery channel of the Basic Native Trading gateway, replaying server initiated messages a client missed on the Real-Time channel for equity instruments of the Johannesburg Stock Exchange and the National Stock Exchange of Australia markets.

### Overview

Each Basic Native Trading server exposes two channels. Orders are submitted on the Real-Time channel; the Recovery channel exists so a client that was disconnected can retrieve the server initiated messages generated while it was away, which are not resent on the Real-Time channel when it reconnects. A client must already hold a Real-Time session before logging in to Recovery, using the same Interface User CompID and password, and any New Password supplied on the Recovery Logon is ignored.

The client sends a Missed Message Request naming a partition and the sequence number immediately after the last message it received, one request per partition. The server answers with a Missed Message Request Ack, replays the messages, and closes the run with a Transmission Complete. A single request returns a bounded number of messages and a client may issue a bounded number of requests a day, with the Transmission Complete or the Ack carrying the status when either limit is reached. Duplicate messages are possible, so clients discard on partition and sequence number.

### Transport

Separate Tcp session from the Real-Time channel, carrying the same length prefixed native framing, on which the client requests missed messages by partition and sequence number.

### Key Characteristics

- **Server initiated messages only** - Replays Execution Report, Order Cancel Reject, Order Mass Cancel Report, News and Business Reject; order entry messages never appear on this channel
- **Requires a Real-Time session** - Logon is rejected unless the client is already connected to the Real-Time channel
- **Per partition replay** - Recovery is requested and delivered one matching partition at a time
- **Millennium native encoding** - Four byte message header with little endian binary fields

