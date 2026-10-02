## AsciiItch: Nasdaq ascii market data message format (fixed length ascii lines)

Fixed length ascii message format of the early Nasdaq direct data feeds: TotalView-ITCH 1.00 through 3.2 and the ascii editions of Nasdaq Last Sale (NLS), NOIView, the PSX Best Bid and Offer, MatchView (formerly the OUCH Pricing Feed) and the Nasdaq Canada CHIXMD and CHIXMMD feeds. Each message is a line of printable ascii fields that opens with a timestamp and a one character message type.

### Overview

The feeds are made up of a series of sequenced messages, variable in length by message type, typically delivered by a higher level protocol that takes care of sequencing and delivery: SoupTCP, compressed SoupTCP or MoldUDP.

All numeric fields are ascii digits right justified and padded on the left with spaces; alpha fields are left justified and padded on the right with spaces. Prices are given in decimal format with 6 whole number places followed by 4 decimal digits, the decimal point implied by position (TotalView-ITCH 1.00 writes 9 whole digits, the point and 10 decimals). Timestamps are milliseconds, or in the earliest editions hundredths of seconds, past midnight Eastern Time.

Only the TotalView-ITCH documents name the protocol ITCH; the NLS, NOIView, BBO, MatchView and CHIXMD documents describe the same fixed width ascii line format under their product names. Later editions of each product moved to the binary Itch format.

### Transport

MoldUDP multicast: sequenced packets of messages, with a rerequest service for missed messages. SoupTCP session, plain or compressed: sequenced data packets whose delivery and order the session guarantees.

### Key Characteristics

- **Fixed length ASCII** - Every message type is a fixed length line of printable ascii fields
- **Timestamp and type** - Each message opens with a timestamp and a one character message type
- **Implied decimal prices** - Prices are 6 whole and 4 implied decimal digits, space padded on the left

