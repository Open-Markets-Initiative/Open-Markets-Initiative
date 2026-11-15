## CoinbaseDerivatives Rest: Coinbase Derivatives Public Rest Api

Json Rest api for Coinbase Derivatives firm administrators: firm position, product and product group limits, positions, firms and users, the kill switch and trading unlock, funding rates, instrument details and valid series, and block trade booking and reference data.

### Overview

The Coinbase Derivatives public Rest api is the OpenAPI 3.0 document cde-public-api-spec.json published on the Coinbase developer platform. Every request and response is application/json unless an operation states otherwise, and a request is authenticated by an Hmac-Sha-256 signature of its timestamp, method, path and body made with an api key created in the Derivatives Command Center.

The api grew from the firm limit, position and kill switch endpoints of August 2025 to v2 position and limit endpoints, instrument details, and block trade booking and reference data with Trade at Settlement fields in 2026.

### Transport

Https requests signed with the CB-ACCESS-KEY, CB-ACCESS-PASSPHRASE, CB-ACCESS-SIGN and CB-ACCESS-TIMESTAMP headers, each answered with an http status and an application/json (or text/plain) body.

### Key Characteristics

- **Json over https** - Request bodies and responses are application/json, with http status codes for success and failure
- **Signed requests** - Hmac-Sha-256 access signature over timestamp, method, path and body
- **Risk administration** - Firm position, product and product group limits, kill switch and trading unlock
- **Block trades** - Block trade booking, history and the accounts, entities and traders that may book them

