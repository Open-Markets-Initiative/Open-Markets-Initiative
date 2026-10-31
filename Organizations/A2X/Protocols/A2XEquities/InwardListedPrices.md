## A2XEquities Inward Listed Prices: A2X Markets inward listed prices reference data file

A2X Markets daily file of its inward listed securities with their opening price and previous closing price and the sources of each.

### Overview

The first line is a header row naming the columns, each following line one security or tick level, its columns separated by a comma (A2X Reference Data Specification, section 2.5).

### Transport

Daily files generated at 03:00 UTC in the refdata folder of A2X's FTP server (FTP and SFTP over a direct connection, SFTP over the internet from a whitelisted address), each with an .md5 checksum file (InwardListedPrices-[YYYYMMDD].csv).

### Key Characteristics

- **Reference files** - One file per day, not a live feed; the market data feed's Security Definition messages carry the same securities

