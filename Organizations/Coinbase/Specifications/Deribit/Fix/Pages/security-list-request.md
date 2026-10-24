> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# Security List Request(x) — Production FIX API

> SecurityListRequest(x) requests the full list of tradable instruments from the Deribit production FIX API, filterable by underlying and product kind.

The `SecurityListRequest`(`x`) message is used to return a list of securities
(instruments) from the Deribit.

### Arguments

| Tag  | Name                           | Type    | Required | Comments                                                                                                                                                                                                                                                                                                                                                                        |
| ---- | ------------------------------ | ------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 320  | `SecurityReqId`                | String  | Yes      | A user-generated ID for this request. This can be used to match the request to the response                                                                                                                                                                                                                                                                                     |
| 559  | `SecurityListRequestType`      | int     | Yes      | 0 or 4 – in any case list of instruments is returned                                                                                                                                                                                                                                                                                                                            |
| 263  | `SubscriptionRequestType`      | int     | No       | Subscription Request Type to get notifications about new or terminated instruments. Valid values: <ul><li> `0` = Snapshot,</li> <li>`1` = Snapshot + Updates (Subscribe),</li> <li>`2` = Disable previous Snapshot + Update Request (Unsubscribe)</li></ul>                                                                                                                     |
| 9013 | `DisplayMulticastInstrumentID` | Boolean | No       | **Custom tag**, default is false (`N`). If the tag is present and set to 'Y', then symbol entries will include the Multicast identifier of the Symbol (if applicable). See `NoSecurityAltID`(`454`) below                                                                                                                                                                       |
| 9018 | `DisplayIncrementSteps`        | Boolean | No       | **Custom tag**, default is false (`N`). If the tag is present and set to 'Y', then symbol entries will include the Price Increment steps of the Symbol (if applicable). See `NoTickRules`(`1205`) below                                                                                                                                                                         |
| 15   | `Currency`                     | String  | No       | First currency of the currency pair for limiting the resulted list. Required if `SecondaryCurrency`(`5544`) specified.                                                                                                                                                                                                                                                          |
| 5544 | `SecondaryCurrency`            | String  | No       | Second currency of the currency pair for limiting the resulted list. Default is USD if `Currency`(`15`) is specified. Current API doesn't support queries by `SecondaryCurrency` only, so `Currency` (`15`) is mandatory if `SecondaryCurrency` is present. In current implementation `SecondaryCurrency` is ignored in subscription when `SubscriptionRequestType` (`263`) = 1 |
| 167  | `SecurityType`                 | String  | No       | Optional parameter for limiting output by the `SecurityType`. Describes type of security.<p> Possible values: <ul><li>`FXSPOT` for currency exchange spot</li><li>`FUT` for futures,</li><li> `OPT` for options,</li> <li> `FUTCO` for future combo,</li> <li>`OPTCO` for option combo</li><li>`INDEX` for indexes</li></ul> </p>                                               |

### Response

The server will respond with a [`Security List`(`y`)](/fix-api/production/security-list) message,
where the `SecurityReq`(`320`) is equal to that of the request.


## Related topics

- [Security List(y) — Production FIX API](/fix-api/production/security-list.md)
- [Security Definition Request(c) — Production FIX API](/fix-api/production/security-definition-request.md)
- [User Request(BE) — Production FIX API](/fix-api/production/user-request.md)
- [Security Status Request(e) — Production FIX API](/fix-api/production/security-status-request.md)
- [Order Mass Cancel Request(q) — Production FIX API](/fix-api/production/order-mass-cancel-request.md)
