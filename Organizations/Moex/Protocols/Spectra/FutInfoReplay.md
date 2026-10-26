## Spectra Fut Info Replay: SIMBA Spectra Futures Instrument Replay

Looping reference data for the futures side of the Moex derivatives market: futures, calendar spreads and the collateral futures for equity options. Carries one security definition per instrument, the trading session status, the discrete auction windows and the group-level trading statuses, broadcast in a loop so a subscriber can build the instrument universe at any point and close the round on the sequence reset. Published on the FUT-INFO groups separately from the options reference data so a subscriber can take only the instrument types it trades.

### Transport

Udp multicast on the FUT-INFO groups, duplicated as an A and a B group, looping the instrument set at a server-side rate limit in snapshot packet framing.

### Key Characteristics

- **Instrument reference data** - One security definition per futures instrument, looped
- **Cycle sequencing** - Numbers restart at one and a sequence reset closes the round
- **Discrete auction windows** - Opening auction start and the interval it may complete in
- **Group statuses** - Halt type and trade mode masks at security group level
- **Simple Binary Encoding** - Fix messages encoded to the Sbe version 1 standard against a published schema
- **Paired multicast streams** - Every stream is broadcast twice on separate groups for arbitration

