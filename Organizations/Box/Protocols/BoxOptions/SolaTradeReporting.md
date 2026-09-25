## BoxOptions Sola Trade Reporting: Box Options Exchange Atr Specifications Guide

Automated Trade Reporting encoding of the Box Options Exchange post trade interface, used to report executed trades and their cancellations to clearing participants and to let participants allocate a trade or give it up to another firm.

### Transport

Tcp via the Box Atr session, each message a fixed extent opened by a twenty eight byte header and closed by an end of text, with signon, circuit assurance and a restart request for recovering a gap.

