## A2XEquities Tick Comma: A2X Markets tick comma delimited reference data file

A2X Markets daily tick table file, comma delimited, otherwise identical to the tab delimited file.

### Overview

The first line is a header row naming the columns, each following line one security or tick level, its columns separated by a comma (A2X Reference Data Specification, section 2.4).

### Transport

Daily files generated at 03:00 UTC in the refdata folder of A2X's FTP server (FTP and SFTP over a direct connection, SFTP over the internet from a whitelisted address), each with an .md5 checksum file (tick_comma-YYYMMDD.csv).

### Key Characteristics

- **Reference files** - One file per day, not a live feed; the market data feed's Security Definition messages carry the same securities

