## A2XEquities Tick: A2X Markets tick reference data file

A2X Markets daily tick table file, tab delimited: each tick table's price levels and increments, named as the security file's tick names.

### Overview

The first line is a header row naming the columns, each following line one security or tick level, its columns separated by a tab (A2X Reference Data Specification, section 2.4).

### Transport

Daily files generated at 03:00 UTC in the refdata folder of A2X's FTP server (FTP and SFTP over a direct connection, SFTP over the internet from a whitelisted address), each with an .md5 checksum file (tick-YYYMMDD.csv).

### Key Characteristics

- **Reference files** - One file per day, not a live feed; the market data feed's Security Definition messages carry the same securities

