## Spectra Opt Info Replay: SIMBA Spectra Options Instrument Replay

Looping reference data for the options side of the Moex derivatives market, carrying options and volatility information. One security definition per instrument plus the trading session status and the group-level trading statuses, broadcast in a loop and closed by a sequence reset. Unlike the futures reference stream it carries no discrete auction message, so the two instrument types get separate transcriptions rather than one shared feed.

### Transport

Udp multicast on the OPT-INFO groups, duplicated as an A and a B group, looping the instrument set at a server-side rate limit in snapshot packet framing.

### Key Characteristics

- **Instrument reference data** - One security definition per options instrument, looped
- **Cycle sequencing** - Numbers restart at one and a sequence reset closes the round
- **Group statuses** - Halt type and trade mode masks at security group level
- **No auction message** - The options reference stream carries no discrete auction, unlike futures
- **Simple Binary Encoding** - Fix messages encoded to the Sbe version 1 standard against a published schema
- **Paired multicast streams** - Every stream is broadcast twice on separate groups for arbitration

