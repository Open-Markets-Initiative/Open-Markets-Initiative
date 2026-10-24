> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# Quote Cancel(Z) — Production FIX API

> QuoteCancel(Z) cancels one or many previously submitted mass quotes on the Deribit production FIX API without needing to submit any replacement quotes.

The `Quote Cancel` (`Z`) message is used by an originator of quotes to cancel his quotes and related orders.

The Quote Cancel message supports cancelation of:

* All quotes
* Quotes for a specific symbol
* All quotes for a security kind (like futures, options)
* By QuoteSetID
* By base Currency of the instruments
* By Delta range

The canceling is accomplished by indicating the type of cancelation in the `QuoteCancelType` (`298`) field and optional additional parameters.

The message is equivalent of the `private/cancel_quotes` and shares the same semantic, so it is quite different from the other exchanges. The same as the Websockets "alter-ego" it is acknowledged only via list (possibly empty) of cancelled orders, namely as the `Order Mass Cancel Report` (`r`) with `ClOrdID` equal to the `QuoteMsgID` of the request, with the affected order ID's and subsequent `Execution Report` (`8`)-s for each individual cancelled order if there are any.

| Tag  | Name              | Type    | Required                          | Comments                                                                                                                                                                                                                                                                                   |
| ---- | ----------------- | ------- | --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1166 | `QuoteMsgID`      | String  | No                                | Optionally used to supply a message identifier for a quote cancel.                                                                                                                                                                                                                         |
| 298  | `QuoteCancelType` | int     | No                                | Default is 4.	Identifies the type of `Quote Cancel` (`Z`) request. 1 = Cancel for `Symbol`(`55`), 2 = Cancel for `SecurityType` (`167`), 4 = Cancel All Quotes, 5 = for `Currency` (`5`), 6 = for `QuoteSetID` (`302`), 7 = for Delta range defined by `MinDelta` and `MaxDelta` see below |
| 55   | `Symbol`          | String  | Required if `QuoteCancelType` = 1 | Common, "human understood" representation of the security, e.g., `BTC-28JUL17`, see instrument naming convention for more details.                                                                                                                                                         |
| 15   | `Currency`        | String  | if `QuoteCancelType` = 2, 5 or 7  | Currency                                                                                                                                                                                                                                                                                   |
| 9031 | `FreezeQuotes`    | Boolean | No                                | Whether or not to reject incoming quotes for 1 second after cancelling                                                                                                                                                                                                                     |
| 167  | `SecurityType`    | String  | If `QuoteCancelType`=2            | Describes type of security.<p> Possible values: <ul><li>`FUT` for futures,</li><li> `OPT` for options,</li> <li> `FUTCO` for future combo,</li> <li>`OPTCO` for option combo</li><li>`SPOT` for spot</li></ul> </p>                                                                        |
| 302  | `QuoteSetID`      | String  | Required if `QuoteCancelType` = 6 | Identifier for the Quote Set                                                                                                                                                                                                                                                               |
| 9032 | `MinDelta`        | float   | Required if `QuoteCancelType` = 7 | Min Delta to cancel by delta range                                                                                                                                                                                                                                                         |
| 9033 | `MaxDelta`        | float   | Required if `QuoteCancelType` = 7 | Max Delta to cancel by delta range                                                                                                                                                                                                                                                         |


## Related topics

- [Deribit Production FIX API Overview](/fix-api/production/overview.md)
- [Changes Log — Production FIX API](/fix-api/production/changes-log.md)
- [Order Mass Cancel Report(r) — Production FIX API](/fix-api/production/order-mass-cancel-report.md)
- [Mass Quote(i) — Production FIX API](/fix-api/production/mass-quote.md)
- [Order Mass Cancel Request(q) — Production FIX API](/fix-api/production/order-mass-cancel-request.md)
