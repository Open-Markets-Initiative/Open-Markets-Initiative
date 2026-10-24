> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# TradeCaptureReportRequestAck(AQ) — Production FIX API

> TradeCaptureReportRequestAck(AQ) acknowledges a TradeCaptureReportRequest on the Deribit production FIX API and indicates whether reports will follow.

The Trade Capture Request Ack message is used to:

* Provide an acknowledgement to a Trade Capture Report Request `AD` in the case
  where the Trade Capture Report Request `AD` is used to specify a subscription.
* The Trade Capture Request was invalid for some business reason, such as the
  request is not authorized, invalid or unknown instrument, party, trading
  session, etc.

| Tag | Name                 | Type   | Required | Comments                                                                                                                               |
| --- | -------------------- | ------ | -------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| 568 | `TradeRequestID`     | String | Yes      | Identifier for the trade request                                                                                                       |
| 569 | `TradeRequestType`   | Int    | Yes      | Describes request type.<p>Valid value:<ul><li>`0` for all trades</li></ul></p>                                                         |
| 571 | `TradeRequestResult` | Int    | Yes      | Result of Trade Request.<p>Valid values:<ul><li>`0` - Successful</li><li>`2` - Invalid type of trade requested</li></ul></p>           |
| 750 | `TradeRequestStatus` | Int    | Yes      | Status of Trade Request.<p>Valid values:<ul><li>`0` - Accepted</li><li>`2` - Rejected</li></ul></p>                                    |
| 55  | `Symbol`             | String | Yes      | Common, "human understood" representation of the security, e.g., <b>BTC-28JUL17</b>, see instrument naming convention for more details |


## Related topics

- [TradeCaptureReportRequest(AD) — Production FIX API](/fix-api/production/trade-capture-report-request.md)
- [TradeCaptureReport(AE) — Production FIX API](/fix-api/production/trade-capture-report.md)
- [Deribit Production FIX API Overview](/fix-api/production/overview.md)
- [Changes Log — Production FIX API](/fix-api/production/changes-log.md)
- [FIX API Changelog](/changelogs/fix.md)
