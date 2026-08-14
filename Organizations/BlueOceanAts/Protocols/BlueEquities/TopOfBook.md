## BlueEquities Top Of Book: Blue Ocean Fix Best Bid And Offer Data

Financial Information eXchange (Fix) top of book market data feed for Blue Ocean ATS, publishing unsolicited best bid, offer and trade snapshots over a Fix session.

### Overview

Fix Top Of Book is the tag value alternative to the binary Memoir Top Of Book feed, carrying the same best bid and offer content over a standard Fix session for participants who prefer a Fix interface to Simple Binary Encoding. Market data is delivered as unsolicited Market Data Snapshot Full Refresh messages, each carrying the symbol and a repeating group of bid, offer and trade entries.

The feed is unidirectional at the business level: the specification defines no client to server application messages, so a subscriber sends only session messages. The client opens a Tcp connection, sends a Logon with provisioned SenderCompID and TargetCompID, and recovers gaps with a ResendRequest. The server backfills business messages with PossDupFlag set and gap fills session messages with SequenceReset. Sequence numbers reset to 1 at the end of each logical session.

### Transport

Tcp Fix session established by the client with a Logon, over which the server publishes unsolicited market data snapshots.

### Key Characteristics

- **Top of book** - Best bid, best offer and trade entries for Blue Ocean listed instruments
- **Fix encoded** - Fixt 1.1 session carrying Fix 5.0 SP2 application messages
- **Unsolicited snapshots** - Market Data Snapshot Full Refresh published without a subscription request, with MDReqID of 0
- **Unidirectional** - No client to server business messages are defined, so the session carries market data one way
- **Session recovery** - ResendRequest backfill with PossDupFlag on business messages and SequenceReset gap fill on session messages
- **Daily sequence reset** - Inbound and outbound sequence numbers return to 1 at the end of each logical session

