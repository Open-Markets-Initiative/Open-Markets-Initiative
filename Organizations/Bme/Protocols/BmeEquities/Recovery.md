## BmeEquities Recovery: BME Equities Recovery

The Recovery server of the equities environment, a Tcp session that gives a client connecting late a snapshot of the current market state rather than a range of past messages. Section 2.3.2 states that the snapshot is asked for in the Logon itself, that the Logon Response states the sequence number the snapshot is based on, and that it ends with a Logout Response saying the snapshot is complete. This specification carries the server's own direction of that session, the four session level messages section 4.1 marks for the Recovery server and the market messages a snapshot is composed of.

### Overview

Only the server's direction is modelled here. Section 2.1 states that the first three fields of any published message are its size, its type and its sequence number, and the message tables bear that out: a client's Logon and Logout carry the size and the type alone. The two directions therefore have different header widths on one session, and are split into a server and a client source as Cme's iLink3 and Mdp3 headers are.

The Recovery server alone carries no Network Status, and no Replay Request Ack or Nack: section 4.1's table of session level messages marks neither for it. It is also the one server whose Logout Response is a success, stating that the snapshot is complete rather than that a session ended.

A snapshot is not the session replayed. Section 2.3.2 states that the server may leave out messages whose events no longer bear on the current market, so what arrives is the current market and security status, the matched trades, the relevant news, the current statistics and the orders presently in the books. For a top of book feed the current top of book stands in place of the orders.

A client stores the multicast messages it receives while the snapshot is arriving, and continues from them once the snapshot is processed, which is why the Logon Response states the sequence number the snapshot was taken at.

### Transport

A session opened with a Logon whose ExpectedSequenceNumber asks for the snapshot, answered by a Logon Response stating the sequence number the snapshot is based on. Silence is filled with Heartbeats, and a Logout Response closes the snapshot.

### Key Characteristics

- **Requested in the Logon** - The snapshot is asked for by the Logon's ExpectedSequenceNumber, not by a request message
- **Logout Response ends it** - The snapshot is complete when the Logout Response arrives
- **Current state, not history** - Messages whose events no longer bear on the current market may be left out
- **Server direction only** - The client's two request messages carry a three byte header and are specified separately
- **Little endian** - Section 3.4.1 states that all numeric values are sent as little endian encoded integers

