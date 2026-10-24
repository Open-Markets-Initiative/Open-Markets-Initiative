> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# MMProtection Reset(MZ) — Production FIX API

> MMProtectionReset(MZ) clears a triggered market maker protection freeze on the Deribit production FIX API so quoting can resume after an MMP event.

**Important: manual admin action is necessary to activate Market Maker
Protection (MMP) for an account.** This message resets Market Maker Protection
(MMP) after triggering.

### Arguments

| Tag   | Name                  | Type   | Required | Comments                                                                                                        |
| ----- | --------------------- | ------ | -------- | --------------------------------------------------------------------------------------------------------------- |
| 20114 | `ProtectionRequestID` | String | Yes      | Unique identifier assigned by the requestor. Will be returned in responses                                      |
| 15    | `Currency`            | String | Yes      | First currency of the currency pair to reset MMP for. e.g. `BTC`, `ETH`                                         |
| 5544  | `SecondaryCurrency`   | String | No       | Secondary currency of the currency pair to reset MMP for. e.g. `USD`, `USDC`, defaults to `USD` if not provided |
| 9019  | `MMPGroup`            | String | No       | A custom tag of MMP Group                                                                                       |

### Response

The server sends `MMProtection Result (MR)` message as a response.


## Related topics

- [MMProtection Limits Result (MR) — Production FIX API](/fix-api/production/mmprotection-limits-result.md)
- [MMProtection Limits (MM) — Production FIX API](/fix-api/production/mmprotection-limits.md)
- [Sequence Reset(4) — Production FIX API](/fix-api/production/sequence-reset.md)
- [Deribit Production FIX API Overview](/fix-api/production/overview.md)
- [Changes Log — Production FIX API](/fix-api/production/changes-log.md)
