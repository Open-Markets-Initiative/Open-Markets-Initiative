## MarketData Normalized: Databento Normalized Dbn Market Data

Normalized market data from over 50 trading venues in the Databento Binary Encoding, delivered as DBN files by the Historical API and batch downloads, and streamed live by the Live API.

### Overview

A historical request names a dataset, a schema, a time range and symbols, and the response is a DBN file: the metadata header, with the symbol mappings that resolve each instrument id over the range, then the records of the requested schema in time order.

### Transport

Https download from the Historical API (timeseries.get_range) or batch jobs, each response a DBN file, usually one zstd frame over the whole file. Live API Raw session on port 13000 of the dataset's live gateway: newline terminated text control messages (greeting, challenge, authentication, subscriptions, session start), then the same DBN stream, its metadata then records, optionally with a ts_out trailer on every record.

### Key Characteristics

- **File delivery** - One DBN file per request, metadata then records
- **Symbol mappings in the metadata** - Instrument ids resolve to symbols through the mappings in the file header

