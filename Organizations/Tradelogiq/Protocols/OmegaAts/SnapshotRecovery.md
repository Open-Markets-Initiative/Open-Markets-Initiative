## OmegaAts Snapshot Recovery: Omega Snapshot Recovery

The Reallocation Server, a SoupTCPBinary service that spins the open orders of the Omega ATS book so a participant can become current after a large data loss without requesting a gap for every message up to that point in the day. The client logs in with session OMEGASSALL in production or OMGATESALL on the test environment, naming the sequence number it wants the book up to, or zero for the latest state; the server answers with a Login Accepted Packet carrying the sequence number of the most recent message applied to the book, then sends a Start-Of-Messages event, the Add Order messages of every open order, and an End-Of-Messages event, after which it disconnects. A Requested Sequence Number of 1 returns the symbol spin of directory and trading action messages instead.

### Overview

Dropped messages can be requested from the Retransmission server over Qtp unicast for small data loss; the Reallocation Server covers large data loss by rebuilding a whole book.

Only open orders are sent in the spin, so the spin carries no message for an order that is no longer in the book. While receiving a spin the participant must buffer any multicast message whose sequence number is greater than the one the Login Accepted Packet named, and apply those messages when End-Of-Messages arrives.

The spin replays a subset of the Itch 5.0 message set: the System Event message carrying Start-Of-Messages and End-Of-Messages, the Add Order message, and for a Requested Sequence Number of 1 the Stock Directory, Extended Stock Directory and Stock Trading Action messages.

### Transport

SoupTCPBinary v1.03 session, a two byte packet length and one byte packet type framing each logical packet, with login, logout and bidirectional heartbeats and guaranteed in order delivery of every sequenced message across socket failures.

### Key Characteristics

- **Book spin** - Add Order messages for every open order, bracketed by Start and End Of Messages
- **SoupTcp Binary session** - Point to point Tcp, the server disconnecting once the spin completes
- **Symbol spin** - A Requested Sequence Number of 1 returns directory and trading action messages
- **Sequence anchored** - The Login Accepted Packet names the most recent message applied to the book
- **Named sessions** - OMEGASSALL in production and OMGATESALL on the test environment

