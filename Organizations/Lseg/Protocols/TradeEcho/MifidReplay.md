## TradeEcho Mifid Replay: MiFID II Post Trade Replay

Replay service retransmitting recently disseminated Trade Echo MiFID II post trade messages over a Tcp session using Group Ticker Plant framing.

### Overview

Replay is the Trade Echo retransmission service, provided over Tcp for subscribers recovering from a small scale gap on the real time multicast channels. A client logs in with a Login Request, submits a Replay Request naming the first sequence number and the number of messages required, and receives the cached messages in their original order.

Each exchange is bracketed by administrative messages, a Login Response and Replay Response reporting acceptance or an explanatory status code, and a Replay and Recovery Complete message marking the end of the retransmission. The server terminates the connection once the request has been serviced, so no logout message is defined.

### Transport

Tcp unicast session using the Lseg Group Ticker Plant (Gtp) unit header framing, carrying administrative messages and the requested application messages.

### Key Characteristics

- **Message retransmission** - Replays published messages by sequence number range from a rolling cache
- **Session administration** - Login, replay request and completion messages bracket each retransmission
- **Request quotas** - Logins and requests are counted per CompId and rejected with an explanatory status
- **Post trade scope** - Carries the MiFID II Trade Report stream together with reference and statistics messages

