## NordicMarkets Consolidated Feed: Nasdaq Nordic Consolidated Tip Market Data

Tagged text market data protocol of the Nasdaq Nordic Genium Consolidated Feed (GCF), disseminating reference data and real-time trades, order books, index, news, corporate action and ESG data for the Nordic and Baltic markets from the GENIUM Market Info system.

### Overview

The Genium Consolidated Feed publishes Nasdaq Nordic market information in TIP, the Transaction Information Protocol of Nasdaq's GENIUM Market Info. Basic data messages describe the exchange and market hierarchy, tradable securities (shares, derivatives, bonds, funds, rights), indices, lists and sectors; real-time messages carry trades, order books, statistics and other market events, alongside index, company news, corporate action, ESG and metal messages.

Every basic data entity is identified by a GENIUM Market Info Id that stays stable over time, and real-time messages reference the entity they concern by that Id, so a client builds its reference data from the Ids. EndOfBasicData marks the basic data of a source system as complete. The order of messages is set by the source systems and may change, and a sequence number of zero on login is treated as one.

### Transport

SoupBinTCP session: the client logs in with username, password, sequence number and session, and every TIP message arrives as a sequenced data packet until the end of session packet when the system closes.

### Key Characteristics

- **Consolidated feed** - Reference data and real-time market data for all Nordic and Baltic markets on one TIP stream
- **SoupBinTCP session** - Login, sequencing and recovery through SoupBinTCP; a sequence number of zero starts from the first message
- **Stable entity Ids** - Basic data Ids do not change from day to day, so clients key their reference data on them
- **Disclosure and ESG data** - Carries company news, corporate actions and ESG disclosures alongside trading data
- **Tagged text encoded** - TIP tag and value pairs of at most 2048 bytes per message

