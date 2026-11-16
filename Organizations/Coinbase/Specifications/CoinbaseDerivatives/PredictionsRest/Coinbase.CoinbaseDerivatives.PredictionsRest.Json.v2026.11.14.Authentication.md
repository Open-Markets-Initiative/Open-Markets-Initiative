> ## Documentation Index
> Fetch the complete documentation index at: https://docs.cdp.coinbase.com/llms.txt
> Use this file to discover all available pages before exploring further.

# Coinbase Derivatives: Predictions REST API Authentication

This page explains how to sign and authenticate Coinbase Derivatives: Predictions REST API requests.

## Signing requests

Every endpoint except `GET /api/ping` requires these four headers:

> [!WARNING]
>
> * `CB-ACCESS-KEY`: The API key.
> * `CB-ACCESS-PASSPHRASE`: The passphrase for the API key.
> * `CB-ACCESS-SIGN`: The Base64-encoded signature.
> * `CB-ACCESS-TIMESTAMP`: The request timestamp.

A request with a missing or invalid header returns `401 UNAUTHORIZED`.

### Selecting a timestamp

`CB-ACCESS-TIMESTAMP` is the number of seconds since the [Unix epoch](http://en.wikipedia.org/wiki/Unix_time) in UTC. It must be within 5 seconds of the API service time. A timestamp outside that window, or one that is not a number, returns `400 BAD_REQUEST`.

### Creating a signature

`CB-ACCESS-SIGN` is an HMAC-SHA256 of the prehash string `timestamp + method + requestPath + body` (where `+` is string concatenation), Base64-encoded.

* `timestamp` is the exact `CB-ACCESS-TIMESTAMP` header value.
* `method` is the HTTP method in upper case, for example `GET` or `POST`.
* `requestPath` is the path of the endpoint, including the `/api` or `/api/v1` prefix. Do not include the host or the query string: query parameters are not signed.
* `body` is the request body exactly as sent, or an empty string when there is no body (for example, on `GET`).

The HMAC key is your API secret **after Base64-decoding it**. Base64-encode the resulting digest with standard Base64 and padding, and send that as `CB-ACCESS-SIGN`.

> [!WARNING]
>
> This differs from the [Coinbase Derivatives: Futures REST API](https://docs.cdp.coinbase.com/api-reference/derivatives-api/rest-api/authentication.md), which uses the secret as is. Signing with the undecoded secret, or sending a hex-encoded digest, returns `401 UNAUTHORIZED`.

## Authorization

After the signature is verified, the API key's user must be active, and the key's Firm or FCM must be active. Each route then requires a permission or a credential level:

| Routes | Requirement |
| :- | :- |
| `POST /api/orders`, `DELETE /api/orders`, `DELETE /api/orders/{order_id}` | `TRADE` permission. An FCM-level key must send the `firm_id` of a Firm under its FCM when placing an order. |
| `POST /api/trading/kill-switch`, `POST /api/trading/unlock` | `RISK_MANAGEMENT` permission on an FCM- or FIRM-level key. The target must be within your own FCM or Firm. |
| `GET /api/v1/series`, `/api/v1/events`, `/api/v1/instruments` and their single-resource routes | `MARKET_DATA` permission. |
| `GET /api/orderbook/{instrument_id}`, `/api/trades/{instrument_id}`, `/api/ticker/{instrument_id}` | `MARKET_DATA` permission. |
| `GET /api/orders`, `GET /api/fills` | No additional permission. Returns only your own orders and fills. |
| `GET /api/positions` | FIRM- or FCM-level key. A FIRM key reads its Firm's positions; an FCM key reads the positions of all its Firms. |
| `GET /api/balances` | FCM-level key. A FIRM-level key gets `403`. |
| `GET /api/firms/{id}` | FIRM-level key, for its own Firm only. Any other ID gets `403`. |
| `GET /api/fcms/{id}` | FCM-level key, for its own FCM only. Any other ID, or a FIRM-level key, gets `403`. |
| `GET /api/ping` | None. No authentication headers are needed. |

A key that lacks the required permission or credential level gets `403 FORBIDDEN`.
