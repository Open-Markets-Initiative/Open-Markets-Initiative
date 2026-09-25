## BoxOptions Sola Order Entry: Box Options Exchange Sail Specifications Guide

Sola Access Information Language encoding of the Box Options Exchange native order entry interface, used by participants to enter, modify and cancel simple and complex orders, quote in bulk, initiate auctions, define complex order instruments and receive execution notices over the Box Sail session.

### Transport

Tcp via the Box Sail session, each message framed by a four byte little endian length and closed by an end of text, for reliable ordered delivery of order entry, quoting and execution notice messages.

