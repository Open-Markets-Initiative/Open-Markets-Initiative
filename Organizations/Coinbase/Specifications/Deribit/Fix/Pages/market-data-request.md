> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# Market Data Request(V) — Production FIX API

> FIX Market Data Request subscribes to order book data and market updates. Learn how to request snapshots and incremental updates via FIX.

`Market Data Request`(`V`) can be used to request market data in snapshot or the
incremental form. Deribit uses his message for order book requests and its
change notification.

### Arguments

| Tag    | Name                      | Type       | Required                         | Comments                                                                                                                                                                                                                                                                                                                                                                                       |
| ------ | ------------------------- | ---------- | -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 262    | `MdReqId`                 | String     | Yes                              | Unique ID assigned to this request                                                                                                                                                                                                                                                                                                                                                             |
| 263    | `SubscriptionRequestType` | int        | Yes                              | Subscription Request Type. Valid values: <ul><li> `0` = Snapshot,</li> <li>`1` = Snapshot + Updates (Subscribe),</li> <li>`2` = Disable previous Snapshot + Update Request (Unsubscribe)</li></ul>                                                                                                                                                                                             |
| 264    | `MarketDepth`             | int        | No                               | See remark about MDUpdateType below                                                                                                                                                                                                                                                                                                                                                            |
| 265    | `MDUpdateType`            | int        | when `SubscriptionRequestType=1` | The type of update to subscribe to. <p>Valid values: <ul><li>`0`= full refresh,</li><li>`1`= incremental refresh</li> </ul></p>                                                                                                                                                                                                                                                                |
| 9011   | `DeribitSkipBlockTrades`  | Boolean    | No                               | To skip block trades. If `9011=Y` then block trades will not be reported. Default is `N`                                                                                                                                                                                                                                                                                                       |
| 9012   | `DeribitShowBlockTradeId` | Boolean    | No                               | To show block trade id. If `9012=Y` and `9012=N` then block trades will include BlockTrade ID as TrdMatchID (880). Default is `N`                                                                                                                                                                                                                                                              |
| 100007 | `DeribitTradeAmount`      | int        | No                               | Amount of trades returned in the snapshot response to request for snapshot of recent trades, default 20, maximum  1000                                                                                                                                                                                                                                                                         |
| 100008 | `DeribitSinceTimestamp`   | int        | No                               | UTC Timestamp in milliseconds (integer number of milliseconds), if specified, the response returns the trades happened since that timestamp, applicable to the request for recent trades snapshot                                                                                                                                                                                              |
|        | Group `MDReqGrp`          |            |                                  |                                                                                                                                                                                                                                                                                                                                                                                                |
| 267    | `NoMdEntryTypes`          | NumInGroup | Yes                              | Number of entry types in the request                                                                                                                                                                                                                                                                                                                                                           |
| =>269  | `MDEntryType`             | int        | Yes                              | <p>Valid values:</p> <ul><li>`0` = Bid (Bid side of the order book),</li><li>`1` = Offer (Ask side of the order book),</li><li>`2` = Trade (Info about recent trades),</li><li>`3` = Index Value (value of Index for INDEX instruments like <b>BTC-DERIBIT-INDEX</b>),</li><li>`6` = Settlement Price (Estimated Delivery Price for INDEX instruments like <b>BTC-DERIBIT-INDEX</b>)</li></ul> |
|        | Group `InstrmtMDReqGrp`   |            |                                  |                                                                                                                                                                                                                                                                                                                                                                                                |
| 146    | `NoRelatedSym`            | NumInGroup | No                               | Number of symbols requested. Necessary if more than 1 Symbol requested                                                                                                                                                                                                                                                                                                                         |
| =>55   | `Symbol`                  | String     | Yes                              | Instrument symbol. See instrument naming convention for more details                                                                                                                                                                                                                                                                                                                           |

When requesting a subscription (`SubscriptionRequestType`=1), the only supported
combinations are:

* `MDUpdateType`=1, `MarketDepth`=0. This will result a [`Market Data - Snapshot`(`W`)](/fix-api/production/market-data-snapshot) with the whole order book, followed by incremental updates (X messages) through the whole order book depth.
* `MDUpdateType`=0, `MarketDepth`=(1,10,20). This results in [`Market Data - Full Refresh`(`W`)](/fix-api/production/market-data-snapshot) messages, containing the entire specified order book depth. Valid values for `MarketDepth` are 1, 10, 20.

If multiple instrument symbols are specified then the system responds with
multiple market data messages corresponding to those instruments.

### Response

If the server is unable to supply the requested data, it will respond with a
[`Market Data Request Reject`(`Y`)](/fix-api/production/market-data-request-reject) message.

If the request called for a snapshot (`SubscriptionRequestType`(`263`)=0), the
server will respond with a [`Market Data - Snapshot/Full Refresh`(`W`)](/fix-api/production/market-data-snapshot) message.

If the request called for a snapshot and subscription
(`SubscriptionRequestType`(`263`)=1), the server will start sending [`Market
Data - Incremental Refresh`(`X`)](/fix-api/production/market-data-incremental) messages.


## Related topics

- [Market Data Request Reject(Y) — Production FIX API](/fix-api/production/market-data-request-reject.md)
- [Market Data Snapshot (W) — Production FIX API](/fix-api/production/market-data-snapshot.md)
- [Market Data Incremental Refresh(X) — Production FIX API](/fix-api/production/market-data-incremental.md)
- [Security Definition Request(c) — Production FIX API](/fix-api/production/security-definition-request.md)
- [Security List Request(x) — Production FIX API](/fix-api/production/security-list-request.md)
