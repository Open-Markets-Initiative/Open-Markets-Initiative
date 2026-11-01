## Dbn: Databento Binary Encoding

Databento's fixed-layout binary encoding of normalized market data: a self-describing metadata header followed by fixed-width little-endian records, one record set shared by every dataset Databento distributes.

### Overview

DBN normalizes each venue's native feed into one set of records - market by order, market by price at depths 0, 1 and 10, best bid and offer, consolidated best bid and offer, open high low close volume bars, instrument definitions, statistics, trading status and auction imbalances - so that one decoder reads every dataset. The record layout is the same for every dataset; datasets differ in which records they offer and in a few venue-specific field codes.

Every record starts with the same 16 byte header: its length in 32-bit words, the record type that selects the rest of the record, the publisher id that denotes the dataset and venue, the instrument id and the event timestamp. Prices are signed 64-bit integers scaled by 1e-9 and timestamps are nanoseconds since the UNIX epoch, with the maximum value of a type meaning undefined.

A metadata header opens every file and stream: the dataset, schema, query range and symbology, and the symbol mappings that resolve the instrument ids. Versions 1, 2 and 3 differ in symbol and asset widths and in a few records, and a file states its version in the metadata.

### Transport

Live data streams from the Databento Live Subscription Gateway over Tcp, after a newline-delimited text authentication and subscription handshake. Historical data is delivered as files, usually one zstd frame over the whole file.

### Key Characteristics

- **Fixed layout** - Records are C structs with fixed-width little-endian fields, decoded without parsing
- **Normalized across venues** - One record set for every dataset Databento distributes
- **Self-describing** - A metadata header states the version, dataset, schema and symbol mappings
- **Length-prefixed records** - Each record carries its length in 32-bit words, so a reader can skip a record it does not know
- **Zstd compressible** - Files and streams are commonly compressed with Zstandard as a whole

