## NsmEquities Ctci: Nasdaq Nsm Equities Ctci

Computer to Computer Interface (Ctci) through the NASDAQ Message Switch, a fixed format text message interface used for NASDAQ Market Center order entry, ACES and risk management, carried over Tcp/Ip in a binary message envelope with session control messages on logical channel zero.

### Transport

Tcp/Ip connection to a NASDAQ well known port: a Logon control message, heartbeat queries every 10 seconds, flow control per logical channel, and up to 63 logical channels each carrying the Ctci messages of one user or device location in a length prefixed envelope closed by the sentinel UU.

