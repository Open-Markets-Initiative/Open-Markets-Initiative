## A2XEquities Security: A2X Markets security file reference data file

A2X Markets daily security reference file, tab delimited: each security's A2X security ID, name, primary venue and A2X Reuters and Bloomberg codes, ISIN, currency, primary MIC, uniform symbology, tick table name, round lot size and Market at Close and test flags.

### Overview

The first line is a header row naming the columns, each following line one security or tick level, its columns separated by a tab (A2X Reference Data Specification, section 2.1).

### Transport

Daily files generated at 03:00 UTC in the refdata folder of A2X's FTP server (FTP and SFTP over a direct connection, SFTP over the internet from a whitelisted address), each with an .md5 checksum file (security-YYYMMDD.csv).

### Key Characteristics

- **Reference files** - One file per day, not a live feed; the market data feed's Security Definition messages carry the same securities

