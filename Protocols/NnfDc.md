## NnfDc: Non-Neat Front End Drop Copy

Nse's drop copy wire encoding as the Protocol for Drop Copy Service version 3 defines it, carrying a member's own order and trade confirmations one way from the host with only session and subscription traffic going the other. Messages ride inside the same twenty two byte packet header the direct interface uses, but the message framing beneath it is this encoding's own: host traffic opens the packet with a two byte Response Message Header and then packs one or more messages into a buffer that may be Lz4 compressed, each message prefaced by a fourteen byte Message Header rather than the forty byte interactive one, while member traffic carries a twenty four byte Request Message Header instead.

### Overview

The packet header is the twenty two bytes of the direct interface encoding: a two byte Length counting the whole packet including itself, a four byte sequence number starting at one and incrementing per packet, and sixteen bytes holding either an Md5 digest or a Gcm authentication tag over the message data alone. A packet is capped at 1400 bytes here rather than the 1024 of the direct interface, so message data reaches 1378.

Message Header is fourteen bytes and not the forty of the interactive circuit: Transaction Code, Error Code, an eight byte Sequence Number and Length. Only Transaction Code keeps its offset of zero. Request Message Header, sent the other way, is twenty four bytes and shares none of that layout, carrying Transaction Code, Trader Id, Sequence Number, Partition Id, Concurrent Login Id and a functionality indicator fixed at D.

Host traffic prefaces the message buffer with a two byte Response Message Header that appears once per packet however many messages are packed behind it. Its second byte is the compression indicator: when set, the whole buffer that follows is one Lz4 block inflating to at most 4096 bytes, and the messages are read out of the inflated buffer. Sequential packing is in Fifo order and messages are unpacked in the same order.

A member connects once to a gateway router over Tls to learn its partitions, then opens one connection per partition. Every message after the unencrypted registration request is Aes 256 Gcm encrypted with a per partition context, so a capture of a partition connection reads no further than that first message without the keys; the twenty two byte packet header is never encrypted and parses either way.

The appendix tables close by directing a reader to drop any transaction code the document does not define, which is only possible because Length frames each packed message. Both older segment documents state that field, there named Message Length, as the length of the entire message including the header, and this generation abbreviates the wording without changing the field.

Two segment documents, Currency Derivatives and Commodity Derivatives, describe the same service in an earlier generation that has no Response Message Header, no compression and no partitions, and prefaces its messages with the forty byte interactive Message Header. That generation is the direct interface encoding rather than this one.

### Transport

Gateway router service, reached over Tls 1.3, carrying only the Gr Request that asks for the member's partition list and the Gr Response that returns it together with the session and cryptographic keys. One drop copy gateway server per partition, named by the Gr Response, carrying the registration, sign on, subscription request and the downloaded confirmations for that partition.

