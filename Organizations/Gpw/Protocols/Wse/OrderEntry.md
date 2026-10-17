## Wse Order Entry: Warsaw Stock Exchange Native Order Gateway

The native order entry interface of Gpw Wats, carrying orders, mass quotes, mass cancellation, market maker commands and off book trade capture reports between an Exchange Member and the gateway over one Tcp connection. Section 4.1 describes it as a point to point service, section 6 the session layer, and section 7 the thirty messages the two sides exchange.

### Overview

The specification declares no packet layer above the message. Every message opens with the same 24 byte header giving its own length, so the connection carries one message after another and a reader walks them by that length. The message index of section 7 shows the length includes the header: Heartbeat, Logout, LogoutResponse and GapFill carry no body of their own and state length 24.

The message set is generated from the publisher's own machine readable schema, trading_port.json, which carries the field layouts, the widths, the value sets and the implied decimal places. The document's section 7 tables are a rendering of the same source and were used to cross check it: all twenty eight messages the section 7 index lists agree with the schema on both the type code and the total length, to the byte.

Two messages are in the schema and in the type code table but have no section of their own and no row in the section 7 index, Test and TestEvent. They are the publisher's internal test messages, and the market data side of the same release carries TestEvent on the same terms.

Numbers carry implied decimals rather than a separator. Section 4.5 states eight places, "All attributes with type Number have 8 decimal places", and names Price as the most common alias of Number.

A direction column is not given. Section 6 states the sender for the session messages outright, and section 7 for the rest in the wording of each message: a request is the Exchange Member's and a response or a notification the gateway's. Heartbeat is sent by both, and Test, which the document does not describe at all, is marked the same way.

Mass quotes are a fixed run, not a counted one. The schema gives quotes as a count byte followed by an array of thirty, and the section 7.12 table states the array at 1080 bytes, thirty quotes of thirty six, whatever the count says is filled.

### Transport

Point to point connection to the trading port, one session per connection identifier, logged in with a token issued by the System Operator.

### Key Characteristics

- **Little endian** - Section 4.5 states the byte order outright, as the market data side does
- **No packet layer** - A message states its own length and the connection concatenates them
- **Schema driven** - Generated from the publisher's trading_port.json rather than transcribed from the document
- **Bidirectional** - One message set for both directions, with no type code used by both sides
- **Implied decimals** - Eight places through Number, with no separator on the wire
- **Nanosecond timestamps** - Unix nanoseconds in UTC, eight bytes, two in every header

