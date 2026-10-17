## BmeFixedIncome Replay: BME Fixed Income Replay

The Replay server of the fixed income environment, a permanent Tcp session beside the multicast feeds that resends any range of messages a listener lost. Section 2.3.1 states that the server sends nothing but Heartbeats until the client asks: a Replay Request names the first and the last sequence number wanted, the server answers with a Replay Request Ack or Nack, and the messages follow in the form the multicast channel sent them. This specification carries the server's own direction of that session, the six session level messages section 4.1 marks for the Replay server and the market messages of the feed being replayed.

### Overview

Only the server's direction is modelled here. Section 2.1 states that the first three fields of any published message are its size, its type and its sequence number, and the message tables bear that out: a client's Logon, Replay Request and Logout carry the size and the type alone. The two directions therefore have different header widths on one session, and are split into a server and a client source as Cme's iLink3 and Mdp3 headers are.

A replayed message is the message the multicast channel sent, so the market message set is the feed's own. The sequence numbers are the feed's too, which is what makes a replay splice into a listener's own stream.

Section 4.2 gives the scenarios the server is meant for and the request each takes: a start of day connection asks from 1 to the sequence number before the first message the channel delivered, and an immediate reconnection asks from the last number received plus one. A Replay Request of 1 to 0 asks for everything from the start of the session.

On a Tcp channel the sequence number may have gaps but is always incremental, except for Heartbeat, Network Status and Reject, which repeat the last number sent and can be neither replayed nor recovered.

### Transport

A permanent session opened with a Logon naming a username and a password, which the server answers with a Logon Response stating the heartbeat interval and the protocol version. Silence is filled with Heartbeats, which repeat the last sequence number rather than consuming one.

### Key Characteristics

- **Range addressed** - A request names the first and the last sequence number, and 1 to 0 means the whole session
- **Server direction only** - The client's three request messages carry a three byte header and are specified separately
- **Same messages as the feed** - A replayed message is the multicast message, with the feed's own sequence number
- **Little endian** - Section 3.4.1 states that all numeric values are sent as little endian encoded integers

