> ## Documentation Index
> Fetch the complete documentation index at: https://docs.deribit.com/llms.txt
> Use this file to discover all available pages before exploring further.

# Mass Quote(i) — Production FIX API

> MassQuote(i) submits many two-sided quotes in a single message on the Deribit production FIX API, letting market makers reduce quoting latency at scale.

Place buy and/or sell orders on one or more instruments. This endpoint can only be used after approval from the administrators. The repeating group structure follows the standard FIX specification, as follows:

| Tag       | Name                | Type              | Required | Comments                                                                                                                                |
| --------- | ------------------- | ----------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| 117       | `QuoteID`           | String            | Yes      | Identifier of a mass quote message. Can be used to match trades to requests. We recommend using an incrementing counter.                |
| 9019      | `MMPGroup`          | String            | Yes      | Custom tag of the MMP group. An MMP group has to be used and only one quote can exist per instrument per side per MMP group.            |
| 62        | `ValidUntilTime`    | UTCTimestamp      | No       | Indicates expiration time of indication for the request, in UTC.                                                                        |
| 296       | `NoQuoteSets`       | NumInGroup        | Yes      | The number of QuoteSets in the repeating group.                                                                                         |
| => 302    | `QuoteSetID`        | String            | Yes      | Identifier for the QuoteSet. Can be used in `Quote Cancel` (`Z`).                                                                       |
| => 304    | `TotNoQuoteEntries` | int               | No       | Total number of quotes for the quote set. IMPORTANT: For now, splitting QuoteSets over several messages is not supported.               |
| => 295    | `NoQuoteEntries`    | NumInGroup        | Yes      | Number of quotes in the QuoteSet repeating group.                                                                                       |
| => => 299 | `QuoteEntryID`      | String            | Yes      | Identifier of the quote. It is echoed in the `Mass Quote Acknowledgement` (`b`).                                                        |
| => => 55  | `Symbol`            | String            | Yes      | Common, "human understood" representation of the security, e.g., <b>BTC-28JUL17</b>, see instrument naming convention for more details. |
| => => 132 | `BidPx`             | Price             | No       | Bid price. If no price is supplied, only the quantity is amended.                                                                       |
| => => 133 | `OfferPx`           | Price             | No       | Offer price. If no price is supplied, only the quantity is amended.                                                                     |
| => => 134 | `BidSize`           | Qty               | No       | Bid quantity in contracts. If no quantity is supplied, only the price is amended.                                                       |
| => => 135 | `OfferSize`         | Qty               | No       | Offer quantity in contracts. If no quantity is supplied, only the price is amended.                                                     |
| => => 18  | `ExecInst`          | MultipleCharValue | No       | Supports post-only and post-only-reject, see `NewOrderSingle` (`D`).                                                                    |

`Mass Quote` (`i`) requires `Cancel On Disconnect` enabled and MMP.

Request example:

```
MassQuote
 QuoteID="MyQuote1"
 9019="default"
   NoQuote_sets=1
     QuoteSetID=1
     TotNoQuoteEntries=2
     NoQuoteEntries=2
	 QuoteEntry_id=1
     Symbol="BTC-PERPETUAL"
     BidPx=41000.0
     OfferPx=42000.0
     BidSize=10.0
     OfferSize=10.0
	 QuoteEntryID=2
     Symbol="BTC-29DEC23"
     BidPx=41500.0
     BidSize=5.0
```

In reply to `Mass Quote` (`i`), the server sends  `Mass Quote Acknowledgement` (`b`) message as well as corresponding `Execution Report`-s (`8`). The reports and acknowledgement are send asynchronously and via different queues, so the precedence of acknowledgement message is not guaranteed.


## Related topics

- [Mass Quote Acknowledgement(b) — Production FIX API](/fix-api/production/mass-quote-acknowledgement.md)
- [Quote Cancel(Z) — Production FIX API](/fix-api/production/quote-cancel.md)
- [Deribit Production FIX API Overview](/fix-api/production/overview.md)
- [Changes Log — Production FIX API](/fix-api/production/changes-log.md)
- [Order Mass Cancel Report(r) — Production FIX API](/fix-api/production/order-mass-cancel-report.md)
