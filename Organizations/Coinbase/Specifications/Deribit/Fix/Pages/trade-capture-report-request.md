> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# TradeCaptureReportRequest(AD) — Production FIX API

> TradeCaptureReportRequest(AD) requests historical or streaming trade capture reports on the Deribit production FIX API, filterable by trade criteria.

Request one or more trade capture reports based upon selection criteria provided
on the trade capture report request.

| Tag | Name                      | Type   | Required | Comments                                                                                                                                                                                                                                                        |
| --- | ------------------------- | ------ | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 568 | `TradeRequestID`          | String | Yes      | Identifier for the trade request                                                                                                                                                                                                                                |
| 569 | `TradeRequestType`        | Int    | Yes      | Describes request type.<p>Valid value:<ul><li>`0` for all trades</li></ul></p>                                                                                                                                                                                  |
| 55  | `Symbol`                  | String | Yes      | Common, "human understood" representation of the security, e.g., <b>BTC-28JUL17</b>, see instrument naming convention for more details                                                                                                                          |
| 263 | `SubscriptionRequestType` | char   | No       | Used to subscribe / unsubscribe for trade capture reports If the field is absent, the value 1 will be the default (subscription). Valid values:<p><ul><li>1 = Subscribe</li><li> 2 = Unsubscribe</li></ul> (Note: 0 = Snapshot is not implemented for now) </p> |


## Related topics

- [TradeCaptureReportRequestAck(AQ) — Production FIX API](/fix-api/production/trade-capture-report-request-ack.md)
- [FIX Drop Copy API](/starbase/fix-drop-copy-api.md)
- [TradeCaptureReport(AE) — Production FIX API](/fix-api/production/trade-capture-report.md)
- [Deribit Production FIX API Overview](/fix-api/production/overview.md)
- [Changes Log — Production FIX API](/fix-api/production/changes-log.md)
