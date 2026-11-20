## NairobiEquities Replay: Nairobi Equities Replay

Tcp retransmission of messages published on the Real-Time channel of the Nairobi Securities Exchange equity trading system, used to recover from a small data loss.

### Overview

The Replay channel retransmits a limited number of the most recent messages published on the Real-Time channel, a count the document leaves as a placeholder (<10,000>). It does not retransmit messages published on the Snapshot channel or on previous trading days.

Retransmitted messages keep their original sequence numbers, and the Time messages are retransmitted with their original timestamps.

A Replay channel is also available from the backup site, but it is activated only in the event of an outage at the main site.

### Transport

Point to point Tcp connection per market data group. The client logs in with a Login Request, requests a range with a Replay Request and logs out with a Logout Request; the server answers a Login Request and a Replay Request with a status, but sends no Login Response to a login with an invalid CompID, password or IP address, and no reply to a Logout Request.

### Key Characteristics

- **Login required** - A Login Request with a CompID and password opens the channel
- **Limited range** - Only the most recent Real-Time messages of the current day
- **Original sequence** - Retransmitted messages keep their Real-Time sequence numbers and timestamps

