## CixAspen Rerequest: CIX Udp Message Recovery

Udp request/response recovery service for the CIX Market Data Feed, letting a recipient re-request a range of missed messages and receive them back in a single Udp packet in the Aspen multicast format.

### Overview

Rerequest is the message-level recovery path for the CIX Market Data Feed. A recipient that detects a gap sends a 20-byte request naming the Market Day Identifier, the Feed Identifier of the rerequest server, the sequence number of the first message wanted, and how many messages to send.

The server replies with a single Udp packet in the same format as the multicast output feed, starting at the requested sequence and carrying up to the requested count, capped by what fits in a 1500-byte MTU. Messages that do not fit are not sent until a subsequent request is made for them. There is no limit on the number of re-requests, so the path is suitable for full recovery even when a recipient starts late in the day.

Responses are addressed to the source address and port of the request packet, so a client may set its source port to the live multicast destination port and let its feed handler process recovered packets as ordinary feed packets. Separate rerequest servers run per feed and per site.

### Transport

Udp datagram carrying a 20-byte rerequest header from client to rerequest server, answered with a single Udp packet of replayed messages sent back to the source address and port of the request.

### Key Characteristics

- **Message level recovery** - Re-request an explicit sequence range rather than a full book snapshot
- **Single packet response** - One Udp packet per request, capped at a 1500-byte MTU
- **Feed format response** - Replayed messages arrive in the Aspen multicast packet format
- **Source port addressing** - Responses return to the source address and port of the request
- **Unlimited re-requests** - No cap on request count, supporting full intra-day recovery

