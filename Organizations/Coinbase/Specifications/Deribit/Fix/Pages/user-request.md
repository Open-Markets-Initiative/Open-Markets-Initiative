> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# User Request(BE) — Production FIX API

> UserRequest(BE) requests user status changes such as logging users in or out of the Deribit production FIX API session for account-level control.

This message is used to request a report on a user's status and user account
info.

### Arguments

| Tag | Name              | Type   | Required | Comments                                                                                                                                                                                                                                                                                                                                                                                                                      |
| --- | ----------------- | ------ | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 923 | `UserRequestID`   | String | Yes      | The request ID                                                                                                                                                                                                                                                                                                                                                                                                                |
| 924 | `UserRequestType` | int    | Yes      | Should be equal to `4` (Request individual user status), only `UserRequestType`=`4` supported for now                                                                                                                                                                                                                                                                                                                         |
| 553 | `Username`        | String | Yes      | API authenticated 'Client ID', user can request only own info, should be the same as for `LOGON`(`A`)                                                                                                                                                                                                                                                                                                                         |
| 15  | `Currency`        | String | No       | Currency of the report. See [`Security List Request`(`x`)](/fix-api/production/security-list-request). Default is BTC. <p>If `CROSS` is given as currency and user has cross collateral enabled, only the following fields are returned:</p><p><ul><li>100001 `DeribitUserEquity`</li><li>100003 `DeribitUserInitialMargin`</li><li>100004 `DeribitUserMaintenanceMargin`</li><li>100013 `DeribitMarginBalance`</li></ul></p> |

### Response

The server will respond with a `User Response`(`BF`) message.


## Related topics

- [User Response(BF) — Production FIX API](/fix-api/production/user-response.md)
- [Deribit Production FIX API Overview](/fix-api/production/overview.md)
- [Order Cancel Request(F) — Production FIX API](/fix-api/production/order-cancel-request.md)
- [Changes Log — Production FIX API](/fix-api/production/changes-log.md)
- [Security Status Request(e) — Production FIX API](/fix-api/production/security-status-request.md)
