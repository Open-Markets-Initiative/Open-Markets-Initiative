## CoinbaseDerivatives Predictions Rest: Coinbase Derivatives Predictions Rest Api

Json Rest api for Coinbase Derivatives Predictions, the binary-outcome event contracts of the Coinbase Derivatives Exchange: the market catalog of series, events and instruments, order entry and cancellation, open orders, fills, positions and balances, firm and Fcm reads, the trading kill switch and unlock, and order book, trade and ticker snapshots.

### Overview

The Predictions Rest api is the OpenAPI 3.0 document cpm-spec.json published on the Coinbase developer platform. Every request and response is application/json with standard http status codes; ids, prices, quantities and other decimal values are strings, and catalog times are Unix epoch milliseconds, firm and Fcm update times and market data times Unix epoch nanoseconds.

List endpoints return one page per request, as data and the cursor of the next page. Error bodies depend on the route: the catalog answers with an error object of code, message and field, orders and account reads with an error name and message.

### Transport

Https requests signed with the CB-ACCESS-KEY, CB-ACCESS-PASSPHRASE, CB-ACCESS-SIGN and CB-ACCESS-TIMESTAMP headers, each answered with an http status and an application/json body (text/plain for GET /api/ping).

### Key Characteristics

- **Json over https** - Request bodies and responses are application/json, with http status codes for success and failure
- **Signed requests** - Hmac-Sha-256 access signature over timestamp, method, path and body
- **Event contracts** - Yes and No contracts on real-world events, priced between 0 and 1 in Usdc
- **Paginated lists** - One page per request with an opaque cursor for the next

