## Recovery: Mtbt Tick Data Recovery

Nse's Tcp recovery service for the tick by tick market data feed. A client that has missed ticks on the multicast stream opens a Tcp session to the Recovery Server and requests a sequence range for a single stream. The server answers with a status message and then replays the missed messages in exactly the wire format used on multicast.

### Overview

The recovery request itself carries no stream header. It is eleven bytes, opening with the message type, followed by the stream identifier and the start and end sequence numbers of the range being requested. To recover a single tick the start and end sequence numbers are set to the same value.

Everything the server sends is framed by the same eight byte stream header as the multicast feed. The response message carries a sequence number of zero; the replayed ticks carry their original sequence numbers, so a client can apply them to its book exactly as if they had arrived on multicast.

A request that fails is answered with an error status rather than an error message, and the member application is expected to send the request again.

### Transport

Recovery session carrying a request for a sequence range, a status response, and the replayed tick messages.

### Key Characteristics

- **Range addressed** - Missed ticks are requested as a start and end sequence number for one stream
- **Format preserving** - Replayed messages use the same framing and layouts as the multicast feed
- **Headerless request** - The recovery request is sent without a stream header; every server message carries one

