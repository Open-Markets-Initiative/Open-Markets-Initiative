## BmeGate: BMEGate Binary Interface

The binary interface of the BME trading system, carrying market information on multicast Udp channels and order entry over Tcp, and serving the equities, fixed income and derivatives environments from one specification. It is the binary alternative to the MEFFGate Fix interface, which describes the same functions in Fix.

### Overview

Section 1.4 declares twelve data types in one table, each named by a letter: U and N for unsigned and signed integers, T for a nanosecond timestamp, D for a day count, C for a character string, B for a bit mask, F for a flag, and P V A R Q for prices, volumes, monetary amounts, rates and quantities. Four of them carry an implicit scale, prices and volumes dividing by ten to the sixth and amounts and rates by ten to the fourth, so nothing on the wire states the scale.

Section 1.4.1 marks each field of each message with the environments that send it, and states that a field not applicable to an environment is not sent at all. One message is therefore a different layout and a different length in each of the three environments, and a decoder must know which environment it is reading.

Section 3.3 assigns a message code that is the single character code of the equivalent Fix message where there is one, so Logon is 0x41 and Logout 0x35, and gives the rest a hexadecimal value below 0x20 or at or above 0x80. Order, quote, execution and trade publications carry a code that reads as a bit mask: within 0x0X the low bits say public or private, active or cancellation, and quote or order, and within 0x1X they say which legs and which sides the message publishes.

Section 3.1 caps a message at 1300 bytes, and section 3.4.2 states that all dates and times are UTC, a timestamp counting nanoseconds and a date counting whole days from 1 January 1970.

### Transport

Market information multicast channels, published as redundant pairs. The full depth channels publish every active order, and the top of book channels publish one or five price levels in its place, with separate retail channels carrying the same depth under their own message types. A channel has no packet header: section 2.1 states that a feed is a series of sequenced messages, each stating its own length, so a datagram holds whole messages to its end. Order entry, a combined market information and order entry channel, and the Replay and Recovery servers that fill gaps in a multicast feed. A Tcp session opens with a Logon naming a username, a password and the protocol version, and the server answers with a Logon Response stating the heartbeat interval; silence is filled with Heartbeats. Section 3.2 states that the protocol does not encrypt and that optional encryption is Tls.

### Key Characteristics

- **Little endian** - Section 3.4.1 states that all numeric values are sent as little endian encoded integers
- **Lettered data types** - Twelve data types, each named by a letter in one table, four of them carrying an implicit decimal scale
- **No packet header** - A datagram is a series of self describing messages, each stating its own length including that length field
- **Fix derived message codes** - A message takes the code of its Fix equivalent where one exists, and order and trade codes read as bit masks
- **Three environments in one specification** - Equities, fixed income and derivatives share the message set and differ field by field
- **Nanosecond timestamps** - Times are nanoseconds since the Unix epoch and dates are whole days from it, both UTC

