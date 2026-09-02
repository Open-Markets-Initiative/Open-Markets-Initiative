## NnfDirect: Non-Neat Front End Direct Interface

Nse's interactive order entry encoding as it is framed on a member's own connection to the exchange, described by the Direct Interface to Exchange Trading System chapter. The messages are the interactive ones, unchanged, but every one of them is carried inside a twenty two byte packet header holding a packet length, a sequence number, and either an Md5 digest or a Gcm authentication tag over the message. The packet length frames the stream in place of the Message Length that the undirected circuit reads from the message header.

### Overview

The packet header is the whole of the difference from the undirected encoding. Packet Length counts the entire packet including its own two bytes, so the message it carries is Packet Length less twenty two, and the specification caps a packet at 1024 bytes.

The header is present whether or not the member encrypts. An encrypting member carries an incrementing sequence number, echoed back on responses to order related requests, and an authentication tag; a non encrypting member sends zero in the sequence number and an Md5 digest computed over the message alone rather than the whole packet.

The first packet of each direction, Secure Box Registration Request and its response, is unencrypted under both encryption methodologies and carries an Md5 digest rather than a tag. Encryption and decryption cover the message only and never the packet header, so the header of every packet is readable even when the messages are not.

The chapter reprints the message header and names the field at offset eight User Id where the interactive chapters call it Trader Id. The two describe the same four bytes.

### Transport

Interactive order entry on the gateway server allocated by the Gateway Router Response, reached directly by the member rather than through a front end.

