> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# MMProtection Limits Result (MR) — Production FIX API

> MMProtectionLimitsResult(MR) is the server response with current MMP settings or a reject on the Deribit production FIX market maker protection endpoint.

**Important: manual admin action is necessary to activate Market Maker
Protection (MMP) for an account.** This message is sent by the server in reply
to [`MMProtection Limits` (`MM`)](/fix-api/production/mmprotection-limits) or [`MMProtectionReset` (`MZ`)](/fix-api/production/mmprotection-reset)

### Response

| Tag   | Name                      | Type    | Required | Comments                                                                                                                                      |
| ----- | ------------------------- | ------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| 20114 | `ProtectionRequestID`     | String  | Yes      | Identifier taken from corresponding [`MM`](/fix-api/production/mmprotection-limits) or [`MZ`](/fix-api/production/mmprotection-reset) message |
| 20117 | `ProtectionRequestResult` | Boolean | Yes      | `Y` = applied or succeeded, `N` = rejected                                                                                                    |
| 58    | `Text`                    | String  | No       | Text describes reject reason or equal to `"success"`                                                                                          |


## Related topics

- [MMProtection Reset(MZ) — Production FIX API](/fix-api/production/mmprotection-reset.md)
- [MMProtection Limits (MM) — Production FIX API](/fix-api/production/mmprotection-limits.md)
- [Deribit Production FIX API Overview](/fix-api/production/overview.md)
- [Changes Log — Production FIX API](/fix-api/production/changes-log.md)
- [FIX API Changelog](/changelogs/fix.md)
