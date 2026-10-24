> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# Security Status Request(e) — Production FIX API

> SecurityStatusRequest(e) subscribes to trading status updates for an instrument on the Deribit production FIX API, covering halts, resumes, and settlement.

This message provides for the ability to request the status of a security.

### Arguments

| Tag | Name                      | Type   | Required | Comments                                                                                                                                                                                                                                                                                                                                   |
| --- | ------------------------- | ------ | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 324 | `SecurityStatusReqID`     | String | Yes      | ID of the request                                                                                                                                                                                                                                                                                                                          |
| 55  | `Symbol`                  | String | Yes      | Instrument symbol. See instrument naming convention for more details                                                                                                                                                                                                                                                                       |
| 263 | `SubscriptionRequestType` | char   | Yes      | `0` = `Snapshot`, `1` = `Snapshot + Updates` (`Subscribe`), `2` = `Unsubscribe` <p>(Please note that our system does not send notifications when currencies are <b>locked</b>. Users are advised to subscribe to the [platform\_state](https://docs.deribit.com/#platform_state) channel to monitor the state of currencies actively.)</p> |

### Response

The server will respond with a [`Security Status` (`f`)](/fix-api/production/security-status)
message.


## Related topics

- [Security Status(f) — Production FIX API](/fix-api/production/security-status.md)
- [Security List(y) — Production FIX API](/fix-api/production/security-list.md)
- [Security Definition(d) — Production FIX API](/fix-api/production/security-definition.md)
- [Order Mass Status Request(AF) — Production FIX API](/fix-api/production/order-mass-status-request.md)
- [User Request(BE) — Production FIX API](/fix-api/production/user-request.md)
