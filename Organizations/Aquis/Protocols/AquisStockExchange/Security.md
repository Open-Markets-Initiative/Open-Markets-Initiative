## AquisStockExchange Security: Aquis Stock Exchange security reference data file

Aquis Stock Exchange daily security reference file, tab delimited: each security's Aquis security ID, name, ticker, ISIN, currency, MIC, tick table, segment, instrument type, board, issuer, country, shares in issue, EMS, market makers, test and tradeable flags, ADT, LIS threshold, sector, quote bases and liquidity.

### Overview

The first line is a header row naming the columns, each following line one row of the file, its columns separated by a tab (AQSE Reference Data Specification, section 3.1).

### Transport

Daily files, available from 04:00 on the Aquis FTP/SFTP service to connected members (security-<yyyymmdd>.csv).

### Key Characteristics

- **Reference files** - One file per day, not a live feed

