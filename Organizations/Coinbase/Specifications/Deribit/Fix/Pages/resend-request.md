> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# Resend Request(2) — Production FIX API

> ResendRequest(2) recovers missed FIX messages from the Deribit production sequence gap by asking the counterparty to resend a specified message range.

The `Resend Request`(`2`) message is used by the server to initiate the
retransmission of messages. This function is utilized if a sequence number gap
is detected, if the receiving application lost a message, or as a function of
the initialization process.

### Arguments

| Tag | Name         | Type | Required | Comments                    |
| --- | ------------ | ---- | -------- | --------------------------- |
| 7   | `BeginSeqNo` | int  | Yes      | The first message to repeat |
| 16  | `EndSeqNo`   | int  | Yes      | The last message to repeat  |


## Related topics

- [Sequence Reset(4) — Production FIX API](/fix-api/production/sequence-reset.md)
- [Deribit Production FIX API Overview](/fix-api/production/overview.md)
- [Request For Positions(AN) — Production FIX API](/fix-api/production/request-for-positions.md)
- [User Request(BE) — Production FIX API](/fix-api/production/user-request.md)
- [Test Request(1) — Production FIX API](/fix-api/production/test-request.md)
