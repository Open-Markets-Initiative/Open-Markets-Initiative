## Mdt: Taifex Market Data Transmission

Record encoding of the Taiwan Futures Exchange market data transmission network. Every message opens with a sixteen byte header carrying an Ascii escape, a transmission code naming the market, a one character message kind that dispatches the body, an information time, an information sequence number, a message version and a body length, and closes with a one byte check sum and a two byte carriage return and line feed terminator. Character fields are fixed width Ascii written X(n); every numeric field is written 9(n) for n decimal digits and transmitted as packed binary coded decimal, two digits to a byte, so a 9(9) price occupies five bytes. Prices carry no scale of their own: the number of decimal digits is named by the decimal locator the product basic data message states for the product.

### Overview

Numbers are packed binary coded decimal rather than binary integers. Appendix 3 of the manual states that the encoding takes the last four bits of each Ascii numeral, so the nine Ascii bytes of a price 123.450 with three decimal digits, 0x30 0x30 0x30 0x31 0x32 0x33 0x34 0x35 0x30, are transmitted as the five bytes 0x00 0x00 0x12 0x34 0x50. A reader that treats those five bytes as a big endian integer reads a different number, so the format is a representation in its own right and not an integer of a smaller width.

The message kind of the header dispatches the body, not the message identifier. The manual labels each format with an identifier such as I020 or B021, but the wire carries a single character message kind, and the transmission code beside it states whether the message belongs to the futures or the options market.

A channel carries a stated subset of the message kinds. Appendix 2 of the manual prints, per channel, which formats that channel provides, and the subsets differ between the regular and the after-hours trading session, so a reader must know its channel to know which formats to expect.

Prices are scaled by a code a sibling message states. The decimal locator of the product basic data message names the number of decimal digits of every price field of that product, and the strike price of an options product carries a decimal locator of its own, so no price field carries its scale in its own definition.

### Transport

Multicast dissemination over the market data transmission network, one group and port per channel, with each channel carrying a stated subset of the message kinds and each market published from two source hosts per server room for redundancy.

### Key Characteristics

- **Packed binary coded decimal** - Every numeric field is nibble packed, two decimal digits to a byte
- **Escape framed records** - A record opens with Ascii escape and closes with a check sum and a carriage return and line feed
- **Character dispatched** - A one character message kind in the header selects the body layout
- **Externally scaled prices** - The decimal locator of the product basic data message names the scale of every price of a product
- **Channel scoped message sets** - Each multicast channel carries a stated subset of the message kinds, differing by trading session

