## CoinbaseDeribit Order Entry: Coinbase Deribit Fix Trading Api

Financial Information eXchange (Fix) 4.4 subset for institutional trading on Coinbase Deribit covering order entry, mass quoting, market data subscription, security reference, trade capture, position reporting, and market maker protection with Deribit custom tags.

### Overview

The Deribit Fix api is a subset of Fix version 4.4 that also includes some tags from version 5.0 and a range of Deribit custom tags for institutional trading in crypto options, futures, and perpetuals. A single session carries the full trading workflow: order entry and cancel/replace, mass quoting with market maker protection, order book market data in snapshot and incremental form, security list and definition reference data, trade capture reports, position reports, and user management.

Sessions authenticate at Logon with a timestamp-and-nonce RawData payload and a SHA256 password hash over the client secret. Custom tags above 100000 can be remapped into the 5000 range at Logon for legacy Fix engines via the UseWordsafeTags flag, and per-connection execution report routing can be tuned with dedicated Logon flags.

### Transport

Tcp (raw or ssl) for authenticated Fix sessions with nonce-based Logon authentication, sequence-number gap recovery, and optional cancel on disconnect.

### Key Characteristics

- **Fix 4.4 subset** - Standard session layer plus 5.0 tags and Deribit custom tags
- **Crypto derivatives trading** - Options, futures, and perpetuals order entry and quoting
- **Mass quoting** - MassQuote, QuoteCancel, and market maker protection messages
- **Market data** - Order book snapshots and incremental refresh over the same session
- **Positions and trade capture** - Position reports and trade capture reports on request
- **Nonce authentication** - Timestamp plus nonce RawData with SHA256 password hash at Logon

