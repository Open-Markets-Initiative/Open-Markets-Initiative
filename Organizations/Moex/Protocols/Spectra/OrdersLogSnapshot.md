## Spectra Orders Log Snapshot: SIMBA Spectra Orders Log Snapshot

Looping snapshot of the active orders book for the Moex derivatives market, the recovery stream a subscriber reads to build its book before applying the incremental feed, and to recover after loss. Each instrument's snapshot is bracketed by the start and end of snapshot flags in the packet header, so a book can be assembled for one instrument without waiting for a full broadcast round. A cycle's messages are numbered from one and closed by a sequence reset, which is how a subscriber knows the round is complete. Broadcast as paired A and B multicast streams in snapshot packet framing, one message per packet.

### Transport

Udp multicast, duplicated as an A and a B group, broadcasting the active orders snapshot in a loop at a server-side rate limit, one Sbe message per datagram.

### Key Characteristics

- **Book snapshot** - The active orders book, looped for late join and recovery
- **Snapshot bracketing** - Start and end of snapshot flags delimit each instrument
- **Cycle sequencing** - Numbers restart at one and a sequence reset closes the round
- **Simple Binary Encoding** - Fix messages encoded to the Sbe version 1 standard against a published schema
- **Paired multicast streams** - Every stream is broadcast twice on separate groups for arbitration
- **Rate limited** - Transmission is throttled server side to bound bandwidth

