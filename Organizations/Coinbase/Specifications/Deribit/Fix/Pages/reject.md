> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# Reject(3) — Production FIX API

> Reject(3) is the session-level reject sent by the Deribit production FIX server for malformed messages or protocol violations, with tag-level reason codes.

The `Reject`(`3`) message should be issued when a message is received but cannot
be properly processed due to a session-level or data structure rule violation.
An example of when a reject may be appropriate would be the receipt of a message
with invalid basic data (e.g. missing tags) which successfully passes
decryption.

### Arguments

| Tag | Name                  | Type   | Required | Comments                                                                                                                                                    |
| --- | --------------------- | ------ | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 45  | `RefSeqNum`           | SeqNum | Yes      | `MsgSeqNum`(`34`) of the rejected message                                                                                                                   |
| 372 | `RefMsgType`          | String | No       | The `MsgType`(`35`) of the FIX message being referenced                                                                                                     |
| 373 | `SessionRejectReason` | int    | No       | Code to identity reason for rejection: <ul><li>`6` = Incorrect data format for value</li><li>`11` = Invalid `MsgType`(`35`)</li><li>`99` = Other</li> </ul> |
| 58  | `Text`                | String | No       | Text string explaining the reason for rejection                                                                                                             |


## Related topics

- [Order Cancel Reject(9) — Production FIX API](/fix-api/production/order-cancel-reject.md)
- [Market Data Request Reject(Y) — Production FIX API](/fix-api/production/market-data-request-reject.md)
- [Deribit Production FIX API Overview](/fix-api/production/overview.md)
- [Changes Log — Production FIX API](/fix-api/production/changes-log.md)
- [Mass Quote Acknowledgement(b) — Production FIX API](/fix-api/production/mass-quote-acknowledgement.md)
