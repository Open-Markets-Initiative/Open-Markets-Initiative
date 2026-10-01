## NtxOptions Cti: Nasdaq Texas Options (NTX) Clearing Trade Interface (CTI)

Binary post trade feed delivering clearing trades, trade corrections and trade cancels with contra side clearing information, plus options directory, complex strategy, trading action and system event messages, for Nasdaq Texas Options (NTX).

### Overview

CTI routes clearing trades to a firm's connection block by OCC clearing number or CMTA, exchange badge or house number, and exchange internal firm identifier. Unlike the executions sent on FIX, SQF or OTTO, a clearing trade carries both the same side and the contra side clearing information and the same side order origin.

Version 3.0 is the all-markets edition of the replatformed options markets: eight character security symbols and Flex auction types, and a 66 byte Options Directory carrying the underlying symbol and a tradable flag. The extended trading hours edition adds MRX pre-trading system events and an extended close closing type.

Earlier editions: version 1.3 is the shared NOM, PHLX and BX Options INET layout (five character symbols, a one byte liquidity code and a four byte trade price); version 2.1 is the BX Options layout after the 2019 replatform onto the ISE system, with an eight byte trade price and version byte 21.

### Transport

Tcp via SoupBinTcp 3.00; every CTI message is a sequenced data packet from the exchange, recoverable by logging in with the last sequence number processed; one connection per matching ring, with a backup connection per primary.

### Key Characteristics

- **Clearing trades** - Trades, corrections and cancels with contra side clearing details
- **SoupBinTcp framed** - Sequenced delivery with recovery from a trading session store
- **Binary encoding** - Fixed layout big endian messages
- **Reference data** - Optional options directory, complex strategy and trading action messages

