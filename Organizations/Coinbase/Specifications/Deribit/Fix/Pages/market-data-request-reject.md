> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# Market Data Request Reject(Y) — Production FIX API

> MarketDataRequestReject(Y) is the Deribit production FIX API server response when a MarketDataRequest is refused, listing reject reason codes and remediation.

If a [`Market Data Request`(`V`)](/fix-api/production/market-data-request) message is not
accepted, the exchange responds with a `Market Data Request Reject`(`Y`) message

### Arguments

| Tag | Name             | Type   | Required | Comments                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| --- | ---------------- | ------ | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 58  | `Text`           | String | No       | Free format text string                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| 262 | `MDReqID`        | String | Yes      | ID of the original request                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| 281 | `MDReqRejReason` | char   | Yes      | Reason for the rejection of a `Market Data Request`(`V`).<p> Possible reasons: <ul><li>`0` = Unknown symbol</li><li>`1` = Duplicate MDReqID(`262`)</li><li>`2` = Insufficient Bandwidth</li><li>`3` = Insufficient Permissions</li><li>`4` = Unsupported SubscriptionRequestType(`263`)</li><li>`5` = Unsupported MarketDepth(`264`)</li><li>`6` = Unsupported MDUpdateType(`265`)</li><li>`7` = Unsupported AggregatedBook (`266`)</li><li>`8` = Unsupported MDEntryType(`269`)</li><li>`9` = Unsupported TradingSessionID(`336`)</li><li>`A` = Unsupported Scope(`546`)</li><li>`B` = Unsupported OpenCloseSettlFlag(`286`)</li><li>`C` = Unsupported MDImplicitDelete(`547`)</li><li>`D` = Insufficient credit </li></ul></p> |


## Related topics

- [Market Data Request(V) — Production FIX API](/fix-api/production/market-data-request.md)
- [Reject(3) — Production FIX API](/fix-api/production/reject.md)
- [Order Cancel Reject(9) — Production FIX API](/fix-api/production/order-cancel-reject.md)
- [Market Data Snapshot (W) — Production FIX API](/fix-api/production/market-data-snapshot.md)
- [Market Data Incremental Refresh(X) — Production FIX API](/fix-api/production/market-data-incremental.md)
