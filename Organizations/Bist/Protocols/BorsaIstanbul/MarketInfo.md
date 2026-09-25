## BorsaIstanbul Market Info: Bist Consolidated Feed Tip Market Data

Tagged text market data protocol of Borsa Istanbul's BISTECH consolidated feed, disseminating reference data and real-time trades, order books and index updates from the GENIUM Market Info system.

### Overview

The BISTECH consolidated feed publishes Borsa Istanbul market information in TIP, the Transaction Information Protocol of Nasdaq's GENIUM Market Info. Basic data messages describe the exchange and market hierarchy, tradable securities (shares, derivatives, funds, rights, fixed income), indices, lists and sectors; real-time messages carry trades, order books and other market events, and index calculation system messages carry index data.

Every basic data entity is identified by a GENIUM Market Info Id that stays stable over time, and real-time messages reference the entity they concern by that Id, so a client builds its reference data from the Ids. EndOfBasicData marks the basic data of a source system as complete, and EndOfStream is sent when the system closes.

### Transport

SoupBinTCP session: the client logs in with username, password and sequence number, and every TIP message arrives as a sequenced data packet until the end of session packet when the system closes.

### Key Characteristics

- **Consolidated feed** - Reference data and real-time market data on one TIP stream
- **SoupBinTCP session** - Login, sequencing and recovery through SoupBinTCP; a sequence number of zero starts from the first message
- **Stable entity Ids** - Basic data Ids do not change from day to day, so clients key their reference data on them
- **Index calculation** - Carries index calculation system messages alongside trading data
- **Tagged text encoded** - TIP tag and value pairs of at most 4096 bytes per message

