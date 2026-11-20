## NairobiEquities Snapshot: Nairobi Equities Snapshot

Tcp snapshots of the order book, trading status, instruments, recent trades, book level statistics, announcements and top of book of the Nairobi Securities Exchange equity trading system, used by late joiners and to recover from a large data loss.

### Overview

A snapshot of the order book is synchronised with a Real-Time sequence number, so a recipient applies the Real-Time messages that follow it to rebuild the order book.

The Snapshot channel also retransmits the trades published on the Real-Time channel during a recent period the document leaves as a placeholder (<10> minutes), and announcements.

Snapshot messages are unsequenced. Their Time messages differ from those published on the Real-Time channel, so the time at which an active order was submitted cannot be recovered from a snapshot.

### Transport

Point to point Tcp connection per market data group. The client logs in with a Login Request, requests a snapshot with a Snapshot Request and logs out with a Logout Request; the server answers with a Snapshot Response, the snapshot messages and a Snapshot Complete.

### Key Characteristics

- **Login required** - A Login Request with a CompID and password opens the channel
- **Synchronised snapshots** - An order book snapshot names the Real-Time sequence number it is synchronised with
- **Trade recovery** - Recent trades and announcements on request

