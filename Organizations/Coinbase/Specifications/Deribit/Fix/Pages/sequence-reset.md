> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# Sequence Reset(4) — Production FIX API

> SequenceReset(4) repositions FIX sequence numbers on the Deribit production FIX session to recover from gaps or apply a graceful counterparty reset.

The `Sequence Reset`(`4`) is to recover from an out-of-sequence condition, to
reestablish a FIX session after a sequence loss. The `MsgSeqNum`(`34`) in the
header is ignored.

### Arguments

| Tag | Name       | Type   | Required | Comments            |
| --- | ---------- | ------ | -------- | ------------------- |
| 36  | `NewSeqNo` | SeqNum | Yes      | New Sequence Number |

### Response

In reply to `Sequence Reset`(`4`), the exchange replies with `Resend
Request`(`2`) with `BeginSeqNo`(`7`) and `EndSeqNo`(`16`) equal to the passed
`NewSeqNo`(`36`) in case of success. In case of wrong arguments, the server
replies with `Resend Request`(`2`) with `BeginSeqNo`(`7`) and `EndSeqNo`(`16`)
equal to the current incoming sequence on the server.

The `Sequence Reset` (`4`) can only increase the sequence number. If a `Sequence
Reset`(`4`) is received attempting to decrease the next expected sequence number
the reply is `Resend Request`(`2`) with `BeginSeqNo`(`7`) and `EndSeqNo`(`16`)
equal to the current incoming sequence on the server.

After sending the correct `Sequence Reset`(`4`), the client should start sending
messages starting from the sequence number equal to the `NewSeqNo`(`36`) passed.


## Related topics

- [Deribit Production FIX API Overview](/fix-api/production/overview.md)
- [Changes Log — Production FIX API](/fix-api/production/changes-log.md)
- [MMProtection Reset(MZ) — Production FIX API](/fix-api/production/mmprotection-reset.md)
- [Logout(5) — Production FIX API](/fix-api/production/logout.md)
- [Resend Request(2) — Production FIX API](/fix-api/production/resend-request.md)
