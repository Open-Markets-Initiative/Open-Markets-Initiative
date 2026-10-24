> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# Logon(A) — Production FIX API

> Logon(A) authenticates and establishes a session on the Deribit production FIX API, covering credentials, heartbeat interval, and cancel-on-disconnect setup.

`Logon`(`A`) must be the first message sent by the client to initiate a session. If
authentication succeeds, the exchange should echo the message back to the
client. If authentication fails, the exchange will respond with a
[`LogOut`(`5`)](/fix-api/production/logout) message with an appropriate reason.

### Arguments

| Tag  | Name                             | Type    | Required | Comments                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| ---- | -------------------------------- | ------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 108  | `HeartBtInt`                     | int     | Yes      | Used to declare the timeout interval in seconds for generating heartbeats                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| 95   | `RawDataLength`                  | Length  | No       | Number of bytes in raw data field. Not required, as the normal RawData is base64 text here                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| 96   | `RawData`                        | data    | Yes      | The timestamp and a Base64 encoded *nonce* (see below)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 553  | `Username`                       | String  | Yes      | API Client ID. This can be obtained from the API tab on your account settings                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| 554  | `Password`                       | String  | Yes      | See below                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| 9002 | `UseWordsafeTags`                | Boolean | No       | If present and set to `Y`, all of the tag numbers for our custom tags start at 5000 instead of 100000. For example, `Volume24h`(`100087`) would become `5078`. This tag can be used due to the fact, that legacy software which implements FIX protocol, doesn't support the extended range for tags, which was defined in later protocol's revisions. This setting stays applied for the remainder of the connection                                                                                                                                      |
| 9001 | `CancelOnDisconnect`             | Boolean | No       | Boolean, to enable or disable session-level cancel on disconnect. Default - false(`N`)                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| 9004 | `DeribitAppId`                   | String  | No       | Registered application Client ID. It is necessary for registered applications only                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 9005 | `DeribitAppSig`                  | String  | No       | Registered application Signature. It is necessary for registered applications only. It is calculated in a similar way to the Password(554) but with Application Secret instead of Client Secret: `base64(sha256(RawData ++ application_secret))`, see below                                                                                                                                                                                                                                                                                                |
| 9007 | `DeribitSequential`              | Boolean | No       | Custom tag to adapt Deribit internal messaging to sequential FIX messaging. If the tag is present and set to `Y`, all messages, including order changes and notifications, are sent through a single queue. This eliminates the distinction between "request/response" and "notifications" queues, which typically handle messages separately. As a result, messages are sent in a sequential order without direct responses. This configuration may cause slower call-return information delivery compared to configurations that use two separate queues |
| 9009 | `UnsubscribeExecutionReports`    | Boolean | No       | Custom tag. Default - false (`N`). If the tag is present and set to 'Y' this connection is unsubscribed from notificational Execution Reports about order changes. Only responses to order operation requests in this connection will be sent as Execution Reports, but no notifications such as orders from other connection or trades initiated by counterparty                                                                                                                                                                                          |
| 9010 | `ConnectionOnlyExecutionReports` | Boolean | No       | Custom tag. Default - false (`N`). If the tag is present and set to 'Y' this connection will receive notificational Execution Reports only for order created in this connection, it won't receive notification for orders created in other connections even within the same subaccount. This tag can be used to split Execution Reports between several connections to the same subaccount                                                                                                                                                                 |
| 9015 | `ReportFillsAsExecReports`       | Boolean | No       | Custom tag, default is false (N). If the tag is present and set to 'Y', then `FillsGrp` is not included into Execution Report, and reported as Execution Reports with `ExecType` = `F`(`TRADE`)                                                                                                                                                                                                                                                                                                                                                            |
| 9018 | `DisplayIncrementSteps`          | Boolean | No       | **Custom tag**, default is false (`N`). If the tag is present and set to 'Y', then symbol entries will include the Price Increment steps of the Symbol (if applicable). See `NoTickRules`(`1205`) below                                                                                                                                                                                                                                                                                                                                                    |

The `RawData`(`96`) tag contains a timestamp and a *nonce*, separated by an
ASCII period (`.`). The *timestamp* needs to be a strictly increasing integer.
We recommend using a timestamp in milliseconds. The *nonce* is composed of
base64-encoded randomly chosen bytes. For safety reasons, it is important that
the *nonce* is sufficiently long and sourced from a cryptographically secure
random number generator. We recommend at least 32 bytes, but the *nonce* can be
up to 512 bytes.

The `Password`(`554`) tag contains a base64 encoded SHA256 hash of the
concatenation of the `RawData`(`96`) content and the client secret:
`base64(sha256(RawData ++ access_secret))`, here `++` denotes operation of the
concatenation.

Optional custom tag `DeribitAppSig`(`9005`) contains a base64 encoded SHA256
hash of the concatenation of the `RawData`(`96`) content and the Application
secret: `base64(sha256(RawData ++ application_secret))`, here `++` denotes
operation of the concatenation. This tag is used for registered applications
only.

`CancelOnDisconnect`(`9001`) controls "Close on Disconnect". If this tag is not
provided, the default setting from the account is used.

### Response

When the login is successful, the server will echo back the request.

If the login was not successful, the server will respond with a
[`Logout`(`5`)](/fix-api/production/logout) message, and close the connection.


## Related topics

- [Logout(5) — Production FIX API](/fix-api/production/logout.md)
- [Changes Log — Production FIX API](/fix-api/production/changes-log.md)
- [Deribit Production FIX API Overview](/fix-api/production/overview.md)
- [Heartbeat(0) — Production FIX API](/fix-api/production/heartbeat.md)
- [User Request(BE) — Production FIX API](/fix-api/production/user-request.md)
