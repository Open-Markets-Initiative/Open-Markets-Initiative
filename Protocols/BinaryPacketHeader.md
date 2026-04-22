## BinaryPacketHeader: MDP 3.0 UDP packet framing

CME's UDP packet header that wraps each Market Data Platform 3.0 multicast datagram, carrying a 32-bit packet sequence number and 64-bit sending time so subscribers can detect gaps and order messages across the MDP channel set (incremental, snapshot, instrument reference, and security definition feeds).

### Overview

CME's Market Data Platform 3.0 (MDP3) distributes market data as SBE-encoded messages over UDP multicast, and every packet begins with the BinaryPacketHeader to give subscribers the metadata they need for gap detection and time synchronization without inspecting the application payload. The packet sequence number is scoped per channel — channels include incremental feeds, instrument replay snapshots, market recovery snapshots, and security definition feeds — so subscribers track one sequence space per multicast group they join.

The sending time field gives nanosecond-precision transmit timestamps assigned by the CME matching engine for each packet, enabling consumers to compute end-to-end latency, order messages across channels, and correlate events with other timestamped data. A packet may contain multiple SBE messages; all share the same packet sequence number and sending time, with per-message sequence numbers carried inside the SBE payload where relevant.

Because UDP multicast delivery is unreliable, MDP3 pairs the BinaryPacketHeader with dedicated TCP replay and snapshot feeds. When a subscriber detects a gap by comparing expected and observed packet sequence numbers, it requests retransmission from the CME market data replay service or joins the instrument-replay multicast group to recover missed messages. The BinaryPacketHeader itself does not acknowledge or retransmit — it is a stateless, one-direction framing wrapper.

### Transport

BinaryPacketHeader sits at the start of every MDP 3.0 UDP multicast datagram and carries two little-endian fields: a 32-bit message sequence number that increments once per packet within the channel's sequence space, and a 64-bit sending time in nanoseconds since the Unix epoch. The remainder of the datagram holds one or more SBE-encoded application messages each prefixed with its own SBE message size and schema identifiers.

### Key Characteristics

- **UDP multicast framing** - Wraps every MDP 3.0 multicast datagram with sequencing and timing metadata
- **32-bit packet sequence** - Per-channel monotonically increasing sequence number for gap detection
- **Nanosecond sending time** - 64-bit matching-engine transmit timestamp in nanoseconds since Unix epoch
- **Little-endian** - Header fields use little-endian byte ordering matching the SBE payload
- **Multi-message datagrams** - A single packet may carry multiple SBE messages sharing the header's sequence and time
- **Per-channel scope** - Sequence space is maintained independently per multicast channel
- **Stateless** - Recovery is handled by external TCP replay and instrument-snapshot services
- **SBE payload** - Precedes one or more Simple Binary Encoding application messages

