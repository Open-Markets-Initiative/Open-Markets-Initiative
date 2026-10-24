> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# Request For Positions(AN) — Production FIX API

> RequestForPositions(AN) requests a snapshot of open positions from the Deribit production FIX API, returned to the client as PositionReport messages.

`Request For Positions`(`AN`) is used by the owner of a position to request a
Position Report.

### Arguments

| Tag | Name                      | Type   | Required | Comments                                                                                                                                                                                                                                                    |
| --- | ------------------------- | ------ | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 710 | `PosReqID`                | String | Yes      | Unique identifier for the `Request for Positions`(`AN`) as assigned by the submitter                                                                                                                                                                        |
| 724 | `PosReqType`              | int    | Yes      | `0` = Positions (currently)                                                                                                                                                                                                                                 |
| 263 | `SubscriptionRequestType` | int    | No       | Subscription Request Type to get notifications about new or terminated instruments. Valid values: <ul><li> `0` = Snapshot,</li> <li>`1` = Snapshot + Updates (Subscribe),</li> <li>`2` = Disable previous Snapshot + Update Request (Unsubscribe)</li></ul> |
| 15  | `Currency`                | String | No       | To request for certain currency only. If it is missing, all currencies are reported                                                                                                                                                                         |

### Response

The server will respond with a [`Position Report`(`AP`)](/fix-api/production/position-report)
message.


## Related topics

- [Position Report(AP) — Production FIX API](/fix-api/production/position-report.md)
- [Deribit Production FIX API Overview](/fix-api/production/overview.md)
- [Changes Log — Production FIX API](/fix-api/production/changes-log.md)
- [User Request(BE) — Production FIX API](/fix-api/production/user-request.md)
- [Test Request(1) — Production FIX API](/fix-api/production/test-request.md)
