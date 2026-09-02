## Eobi: Enhanced Order Book Interface

Bse's full depth order by order market data feed, publishing every visible order together with executions, auction events, instrument state, and intraday complex instrument definitions. It is the higher transparency companion to the netted Emdi feed, and is carried as fixed length little endian binary on Ip multicast.

### Overview

Bse Eobi is a licensed deployment of the T7 Enhanced Order Book Interface and inherits its datagram model. Each datagram opens with a thirty two byte Packet Header and is terminated on a product boundary, so one datagram never mixes order book updates for more than one product. The Packet Header names the product through Market Segment Id, the partition through Partition Id, and stamps the datagram with a contiguous Appl Seq Num and a send time.

An atomic unit of work processed by the matching engine is normally delivered in a single datagram. When it does not fit, the unit is spread across several datagrams and Completion Indicator is set to Incomplete on all but the last, letting a subscriber gather the whole event before applying it.

Every message behind the Packet Header carries its own eight byte message header of Body Len, Template Id, and Msg Seq Num. Template Id selects the fixed layout that follows, so a subscriber dispatches on Template Id and steps to the next message by Body Len.

Recovery runs out of band. A subscriber joining mid day buffers the incremental channel while replaying the snapshot channel, then applies any buffered message whose Msg Seq Num exceeds the Last Msg Seq Num Processed carried in the snapshot. A snapshot cycle for a product opens with a Product Summary, then repeats an Instrument Summary followed by that instrument's visible orders, and closes when Completion Indicator is set to Complete.

An order is identified by the combination of Security Id, Trd Reg Ts Time Priority, and Side rather than by an order id. Price levels, aggregation, and synthetic prices are not published and must be derived from the individual orders.

### Transport

Two Ip multicast channels per product, an incremental channel carrying order book updates and a snapshot channel carrying periodic recovery cycles, each duplicated as Service A and Service B under the Live Live concept.

### Key Characteristics

- **Full unnetted book** - Every visible order is published individually with no depth restriction
- **Fixed length binary** - Little endian fixed width layouts selected by Template Id, with explicit padding fields holding eight byte alignment
- **Out of band recovery** - Incremental and snapshot messages are delivered on separate multicast channels and synchronised through Last Msg Seq Num Processed
- **Live Live** - Each channel is disseminated twice, as Service A and Service B, for redundancy
- **Product scoped datagrams** - A datagram is terminated on the product boundary and carries updates for one product only
- **Fix derived** - Field names and tag numbers follow the Fix standard, with private U prefixed message types for the market data layouts
- **Nanosecond timestamps** - Times are nanoseconds since the Unix epoch in Utc

