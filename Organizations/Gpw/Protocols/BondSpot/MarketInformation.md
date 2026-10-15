## BondSpot Market Information: BondSpot Market Information

The Market Information service of BondSpot over the NYSE Technologies Universal Trading Platform, carrying the state of each instrument and of the market itself, the instrument reference data flow and the session summary. The service uses a push based publishing model, publishing data as it becomes available. Section 1.2.1 of the specification names the message types of this feed for this venue, which are 516 523 537 539 550 551 556 561.

### Overview

Every packet opens with the same 16 byte header, so a client implements line level protocol processing once and then parses only its choice of message. The header gives the packet length including itself, the packet type, a per stream packet sequence number used for gap detection, a send time, the service id, a delivery flag and the number of messages in the packet. Each message that follows carries its own two byte size, which excludes those two bytes, and a two byte type.

The document states one packet type, 501 for Market Data messages, for every feed it specifies. The feeds are told apart by their service id, not by the packet type.

Prices carry no scale of their own. A price is an integer divided by ten to the power of a scale code that travels beside it in the same message, so a consumer reads the scale code before it can value the price.

The same document specifies the Warsaw Stock Exchange and BondSpot feeds and gives each service a separate message list per venue, so the two venues are separate specifications rather than one. BondSpot carries no instrument state change, indicative matching price, short sale change, generic message or open position, and the Warsaw Stock Exchange carries no yield to maturity.

A code can mean different things on the two venues. The type of price of the 241 Price Update message reads 30 as the first traded price of the day for the Warsaw Stock Exchange and as a change of first price for BondSpot, and takes four values on BondSpot that the Warsaw Stock Exchange never sends; the instrument category of the 556 Referential message reads O as a bond for the Warsaw Stock Exchange and as a treasury bill or bond not quoted on information fixing for BondSpot. The value sets are therefore declared per venue.

The byte order is the one trait no sentence of the document states. Its 16 byte packet header, its length prefixed messages, its Format column vocabulary and its NYSE Technologies authorship are those of the Universal Trading Platform Xdp family, whose sibling specification for the same framing states network byte order, so the integers are read big endian. A capture is what would confirm it.

### Transport

Multicast stream identified by a service id, whose values the companion XDP CDE Configuration document states rather than this specification. A real time stream and a refresh stream carry the same messages, the refresh stream ZliB compressed, and the delivery flag of each packet says which form it is.

### Key Characteristics

- **Common packet header** - A 16 byte header on every packet, counting the messages that follow it
- **Length prefixed messages** - Each message carries a two byte size excluding itself and a two byte type
- **Runtime scaled prices** - A price is an integer valued against a scale code carried beside it, not a fixed number of decimal places
- **Compressed refresh** - Refresh and compressed real time streams are ZliB compressed and flagged by the delivery flag
- **Per venue message sets** - One document serves two venues, each service naming its own message list per venue
- **Service id addressed** - A feed is identified by its service id, which the companion configuration document states

