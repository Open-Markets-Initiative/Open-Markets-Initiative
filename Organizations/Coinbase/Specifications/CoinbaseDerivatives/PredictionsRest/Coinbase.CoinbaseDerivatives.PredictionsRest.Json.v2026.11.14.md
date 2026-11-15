> ## Documentation Index
> Fetch the complete documentation index at: https://docs.cdp.coinbase.com/llms.txt
> Use this file to discover all available pages before exploring further.

# Welcome to the Coinbase Derivatives: Predictions REST API

> [!TIP]
>
> The REST endpoints are listed in the sidebar under **REST Endpoints**. Every endpoint except `GET /api/ping` requires the signed headers described in [Authentication](https://docs.cdp.coinbase.com/api-reference/derivatives-predictions-api/rest-api/authentication.md).

## Basics

All requests and responses use the `application/json` content type and standard HTTP status codes.

| Path prefix | Routes |
| :- | :- |
| `/api/v1` | Market catalog: Series, Events, and Instruments. |
| `/api` | Orders, account reads (open orders, fills, positions, balances), firm and FCM reads, trading lock, and market data snapshots. |

Hosts for each environment are listed on the [Coinbase Derivatives: Predictions Connectivity](https://docs.cdp.coinbase.com/derivatives-predictions/connectivity.md) page.

## Data types

| Type | Format |
| :- | :- |
| Identifiers | Strings containing a positive decimal integer, with no sign or leading zeros, up to the signed 64-bit maximum. IDs are strings so that clients without exact 64-bit integers do not lose precision. An invalid ID returns `400`. |
| Decimals | Prices, quantities, and other decimal values are strings. Equal values may be returned with different numbers of trailing zeros. |
| Currency | Prices and contract notional are in USDC. |
| Timestamps | Series, Event, and Instrument times are Unix epoch milliseconds as numbers. Firm and FCM `updated_at` is Unix epoch nanoseconds as a number. Fill `timestamp` is an ISO-8601 UTC string. Market data `timestamp_ns` and `last_trade_timestamp_ns` are Unix epoch nanoseconds as numbers. |
| Enums | Uppercase strings. |
| Nulls | Optional fields without a value are returned as `null`. |

### Tickers

Tickers are opaque ASCII strings up to 128 bytes. A ticker is never all digits: in an `id_or_ticker` path segment, an all-digit value is read as an ID and anything else as a ticker. Do not parse meaning from a ticker.

## Pagination

List endpoints return one page per request.

| Parameter | Description |
| :- | :- |
| `limit` | Page size. Default `100`. Catalog lists (`/api/v1/series`, `/api/v1/events`, `/api/v1/instruments`) accept `1` to `1000`. `/api/orders`, `/api/fills`, and `/api/positions` accept `1` to `500`. |
| `cursor` | Opaque cursor from the previous page. Omit it on the first request. |

Every list response has two fields:

| Field | Description |
| :- | :- |
| `data` | The page of results. An empty array when nothing matches. |
| `cursor` | Cursor for the next page, or `null` when there is no next page. A cursor works only on the endpoint that returned it. |

`GET /api/balances` returns a single object and is not paginated.

## Status codes

### Success

A successful request returns HTTP `200`. The response body for each endpoint is documented under **REST Endpoints**.

### Errors

Errors return HTTP `4xx` or `5xx`. The error body depends on the route:

| Routes | Error body fields |
| :- | :- |
| Authentication and authorization, on every route | `error`: the error name, for example `UNAUTHORIZED`. `message`: a description of the cause. |
| Catalog (`/api/v1`) | `error.code`: for example `INVALID_PARAMETER` or `NOT_FOUND`. `error.message`: a description. `error.field`: the request parameter at fault, or `null`. |
| Orders, account reads, firms and FCMs, trading lock | `error`: the error or reject reason name, for example `INVALID_FIELD`. `message`: a description. |
| Market data snapshots (`/api/orderbook`, `/api/trades`, `/api/ticker`) | `reason`: the error name. `message`: a description. Returned with HTTP `400`. |

### Common error codes

| Status | Reason |
| :- | :- |
| 400 | Bad Request. The request is invalid, or `CB-ACCESS-TIMESTAMP` is invalid or outside the allowed window. A rejected order also returns `4xx`. |
| 401 | Unauthorized. Authentication headers are missing or invalid, or the API key is not active. |
| 403 | Forbidden. The API key lacks the route's permission, or its credential level cannot call the route. |
| 404 | Not Found. A single-resource lookup does not match a visible resource. |
| 408 | Request Timeout. The request was not processed in time. |
| 500 | Internal Server Error. |
| 503 | Service Unavailable. Account reads are temporarily unavailable (`READ_MODEL_UNAVAILABLE`), or a balance is not available yet. A missing balance is never returned as zero. |
