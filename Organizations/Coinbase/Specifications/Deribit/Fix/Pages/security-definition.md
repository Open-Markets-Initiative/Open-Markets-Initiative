> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# Security Definition(d) — Production FIX API

> SecurityDefinition(d) is the server response describing an instrument's contract terms and trading parameters on the Deribit production FIX API.

The Security Definition `d` message is used for the following:

* Accept the security defined in a [`Security Definition Request (c)`](/fix-api/production/security-definition-request) message with changes to the definition and/or identity of the security.
* Reject the security requested in a Security Definition Request message

| Tag   | Name                         | Type         | Required | Comments                                                                                                                                                                                                                 |
| ----- | ---------------------------- | ------------ | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 320   | `SecurityReqID`              | String       | Yes      | Request identifier                                                                                                                                                                                                       |
| 322   | `SecurityResponseID`         | String       | Yes      | Equal to the `SecurityReqID`                                                                                                                                                                                             |
| 323   | `SecurityResponseType`       | int          | Yes      | Type of Security Definition response. <p>Valid values: <ul><li>`2` = accept security proposal with possible revisions as indicated in the message,</li> <li>`5` = reject proposal</li></ul></p>                          |
| 55    | `Symbol`                     | String       | No       | Common, "human understood" representation of the security                                                                                                                                                                |
| 48    | `SecurityID`                 | String       | No       | Takes precedence in identifying security to counterparty.                                                                                                                                                                |
| 22    | `SecurityIDSource`           | String       | No       | `101` = Multi-cast identifier, `102` = Combo instrument identifier                                                                                                                                                       |
| 225   | `IssueDate`                  | UTCTimestamp | No       | Creation timestamp                                                                                                                                                                                                       |
| 873   | `DatedDate`                  | UTCTimestamp | No       | State timestamp                                                                                                                                                                                                          |
| 58    | `Text`                       | String       | No       | Explanatory text string                                                                                                                                                                                                  |
|       | Group `UnderlyingInstrument` |              |          |                                                                                                                                                                                                                          |
| 711   | `NoUnderlyings`              | int          | No       | Number of underlying items in the group, if applicable. Underlying group is present in reply to [`Security Definition Request (c)`](/fix-api/production/security-definition-request) with `SecurityRequestType(321)` = 3 |
| =>311 | `UnderlyingSymbol`           | String       | No       | Combo-instrument symbols in reply to [`Security Definition Request (c)`](/fix-api/production/security-definition-request) with `SecurityRequestType(321)` = 3                                                            |
| 965   | `SecurityStatus`             | String       | No       | Denotes the current state of the Instrument. <p>Valid values: <ul><li>`1` = Active, </li><li>`2` = Inactive, </li><li>`3` = RFQ, </li><li>`4` = Closed,</li> <li>`12` = Archivized</li></ul></p>                         |
|       | Group `InstrmtLegGrp`        |              |          |                                                                                                                                                                                                                          |
| 555   | `NoLegs`                     | int          | Yes      | Number of legs that make up the Security                                                                                                                                                                                 |
| =>600 | `LegSymbol`                  | String       | No       | Non-combo instrument name                                                                                                                                                                                                |
| =>623 | `LegRatioQty`                | int          | No       | Positive or negative adjusted to the strategy definition                                                                                                                                                                 |


## Related topics

- [Security Definition Request(c) — Production FIX API](/fix-api/production/security-definition-request.md)
- [Deribit Production FIX API Overview](/fix-api/production/overview.md)
- [Changes Log — Production FIX API](/fix-api/production/changes-log.md)
- [Security List(y) — Production FIX API](/fix-api/production/security-list.md)
- [Security Status(f) — Production FIX API](/fix-api/production/security-status.md)
