## CxeEquities Last Sale: Cboe Europe CXE Last Sale Trade Tape (Ascii Pitch over Soup 2.0)

Cboe Europe last-sale trade tape for Cboe Europe CXE delivered as Ascii Pitch records framed by Soup 2.0. A single Cboe Europe last-sale feed carries trades for both the BXE and CXE lit books; this per-market reference shares that wire message format.

### Transport

Tcp delivery via Soup 2.0 framing — fixed-length non-control Ascii last-sale records with login, heartbeat, sequencing and replay handled by the Soup envelope.

