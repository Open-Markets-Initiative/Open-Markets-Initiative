> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# Order Mass Cancel Report(r) — Production FIX API

> OrderMassCancelReport(r) is the server report confirming or rejecting a mass cancel operation on the Deribit production FIX API, with affected order counts.

| Tag  | Name                     | Type   | Required | Comments                                                                                                                                                                                                                                                                                                             |
| ---- | ------------------------ | ------ | -------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 11   | `ClOrdID`                | String | No       | Unique Identifier assigned by the client in the [`Order Mass Cancel Request`(`q`)](/fix-api/production/order-mass-cancel-request)                                                                                                                                                                                    |
| 37   | `OrderID`                | String | No       | Unique ID assigned by Deribit for this order                                                                                                                                                                                                                                                                         |
| 530  | `MassCancelRequestType`  | int    | Yes      | Specifies the type of cancellation request. <p>Possible values:<ul><li>`7` = all orders,</li> <li>`5` = orders by security type,</li> <li>`1` = orders by symbol, </li><li>`10` = orders by DeribitLabel</li><li>`11` = quote cancel -- response to ` Quote Cancel` (`Z`) request used in mass quoting</li></ul></p> |
| 531  | `MassCancelResponse`     | int    | No       | If successful, echoes the `MassCancelRequestType`(`530`)                                                                                                                                                                                                                                                             |
| 298  | `QuoteCancelType`        | int    | No       | May be present in case of reply to `Quote Cancel` (`Z`) request. 1 = Cancel for `Symbol`(`55`), 2 = Cancel for `SecurityType` (`167`), 4 = Cancel All Quotes, 5 = for `Currency` (`5`), 6 = for `QuoteSetID` (`302`), 7 = for Delta range                                                                            |
| 58   | `Text`                   | String | No       | 'success', if deletion was successful                                                                                                                                                                                                                                                                                |
| 532  | `MassCancelRejectReason` | String | No       | Reason why deletion failed.<p>Possible values:<ul><li>`1` = Unknown security,</li> <li>`5` = Unknown security type</li></ul> </p>                                                                                                                                                                                    |
| 533  | `TotalAffectedOrders`    | int    | No       | Total number of orders affected by [`Order Mass Cancel Request`(`q`)](/fix-api/production/order-mass-cancel-request)                                                                                                                                                                                                 |
|      | Group `AffectedOrdGrp`   |        |          |                                                                                                                                                                                                                                                                                                                      |
| 534  | `NoAffectedOrders`       | int    | No       | Optional field used to indicate the number of order identifiers for orders affected by the [`Order Mass Cancel Request`(`q`)](/fix-api/production/order-mass-cancel-request)                                                                                                                                         |
| =>41 | `OrigClOrdID`            | String | No       | Required if `NoAffectedOrders`(`534`) > 0. Indicates the client order id of an order affected by the [`Order Mass Cancel Request`(`q`)](/fix-api/production/order-mass-cancel-request)                                                                                                                               |


## Related topics

- [Order Mass Cancel Request(q) — Production FIX API](/fix-api/production/order-mass-cancel-request.md)
- [Quote Cancel(Z) — Production FIX API](/fix-api/production/quote-cancel.md)
- [Execution Reports(8) — Production FIX API](/fix-api/production/execution-reports.md)
- [Mass Quote(i) — Production FIX API](/fix-api/production/mass-quote.md)
- [Order Cancel Reject(9) — Production FIX API](/fix-api/production/order-cancel-reject.md)
