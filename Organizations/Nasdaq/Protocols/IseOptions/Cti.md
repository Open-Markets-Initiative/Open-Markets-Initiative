## IseOptions Cti: Nasdaq ISE Clearing Trade Interface (CTI)

Binary post trade feed delivering clearing trades, trade corrections and trade cancels with contra side clearing information, plus options directory, complex strategy, trading action and system event messages, for Nasdaq ISE.

### Overview

CTI routes clearing trades to a firm's connection block by OCC clearing number or CMTA, exchange badge or house number, and exchange internal firm identifier. Unlike the executions sent on FIX, SQF or OTTO, a clearing trade carries both the same side and the contra side clearing information and the same side order origin.

Version 3.0 is the all-markets edition of the replatformed options markets: eight character security symbols and Flex auction types, and a 66 byte Options Directory carrying the underlying symbol and a tradable flag. The extended trading hours edition adds MRX pre-trading system events and an extended close closing type.

### Transport

Tcp via SoupBinTcp 3.00; every CTI message is a sequenced data packet from the exchange, recoverable by logging in with the last sequence number processed; one connection per matching ring, with a backup connection per primary.

### Key Characteristics

- **Clearing trades** - Trades, corrections and cancels with contra side clearing details
- **SoupBinTcp framed** - Sequenced delivery with recovery from a trading session store
- **Binary encoding** - Fixed layout big endian messages
- **Reference data** - Optional options directory, complex strategy and trading action messages

