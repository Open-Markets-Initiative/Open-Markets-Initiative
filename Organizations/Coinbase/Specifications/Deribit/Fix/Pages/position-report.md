> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# Position Report(AP) — Production FIX API

> PositionReport(AP) is the server-pushed report of open positions on the Deribit production FIX API, sent in response to a RequestForPositions or trade update.

The `Position Report`(`AP`) message is returned by the holder of a position in
response to a [`Request For Positions`(`AN`)](/fix-api/production/request-for-positions) message.

### Arguments

| Tag      | Name                      | Type       | Required | Comments                                                                                                                                                          |
| -------- | ------------------------- | ---------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 721      | `PosMaintRptID`           | String     | Yes      | Unique identifier for this position report                                                                                                                        |
| 710      | `PosReqID`                | String     | No       | Unique identifier for the Request for Positions associated with this report                                                                                       |
| 724      | `PosReqType`              | int        | No       | Used to specify the type of position request being made. `0` = Positions (currently)                                                                              |
| 728      | `PosReqResult`            | int        | No       | Result of a Request for Position.<p>Possible values: <ul><li> `0` = success,</li><li> `1` = unsupported request for positions,</li><li>`99` = other</li></ul></p> |
|          | Group `PositionQty`       |            |          |                                                                                                                                                                   |
| 702      | `NoPositions`             | NumInGroup | No       | Number of position entries following                                                                                                                              |
| =>703    | `PosType`                 | String     | No       | Type of quantity. <p>Possible values:<ul> <li>`TQ` = Transaction Quantity </li></ul></p>                                                                          |
| =>704    | `LongQty`                 | Qty        | No       | Qty for long position (`0` for short position) in Contract units corresponding to the ContractMultiplier in SecurityList                                          |
| =>705    | `ShortQty`                | Qty        | No       | Qty for short position (`0` for long position) in Contract units corresponding to the ContractMultiplier in SecurityList                                          |
| =>55     | `Symbol`                  | String     | No       | Instrument symbol                                                                                                                                                 |
| =>854    | `QtyType`                 | int        | No       | Type of quantity specified in a quantity. Currently only 1 - `Contracts`                                                                                          |
| =>231    | `ContractMultiplier`      | float      | No       | Specifies a multiply factor to convert from contracts to total units                                                                                              |
| =>883    | `UnderlyingEndPrice`      | Price      | No       | Mark price (reference price)                                                                                                                                      |
| =>54     | `Side`                    | char       | No       | Side of order.<p>Possible values:</p> <ul><li>`1` = Buy,</li> <li>`2` = Sell</li></ul>                                                                            |
| =>730    | `SettlPrice`              | Price      | No       | Average price                                                                                                                                                     |
| =>96     | `RawData`                 | String     | No       | Additional info, semi-colon separated: maintenance margin;initial margin;floating P/L                                                                             |
| =>100088 | `DeribitLiquidationPrice` | Price      | No       | Estimated liquidation price                                                                                                                                       |
| =>100089 | `DeribitSizeInCurrency`   | Qty        | No       | Size in the underlying currency, for example BTC or ETH                                                                                                           |


## Related topics

- [Request For Positions(AN) — Production FIX API](/fix-api/production/request-for-positions.md)
- [Execution Reports(8) — Production FIX API](/fix-api/production/execution-reports.md)
- [Order Mass Cancel Report(r) — Production FIX API](/fix-api/production/order-mass-cancel-report.md)
- [TradeCaptureReport(AE) — Production FIX API](/fix-api/production/trade-capture-report.md)
- [TradeCaptureReportRequest(AD) — Production FIX API](/fix-api/production/trade-capture-report-request.md)
