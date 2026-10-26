## Spectra Opt Info Incremental: SIMBA Spectra Options Instrument Incremental

Real-time changes to the options instrument set and to session state, the companion to the looping OPT-INFO replay stream: per-instrument trading status, the mass status packet, group-level halts and trade modes, and trading session transitions. It is the only stream carrying the security definition update report, which restates an instrument's definition after it changes, and like its replay counterpart it carries no discrete auction message.

### Transport

Udp multicast on the OPT-INFO groups, duplicated as an A and a B group, carrying instrument and session status changes as they happen.

### Key Characteristics

- **Status changes** - Per-instrument, mass and group-level trading status updates
- **Definition updates** - The only stream carrying the security definition update report
- **Session transitions** - Trading session open and close with the session type
- **Simple Binary Encoding** - Fix messages encoded to the Sbe version 1 standard against a published schema
- **Transaction timing** - An incremental packet header states when matching began on the change
- **Paired multicast streams** - Every stream is broadcast twice on separate groups for arbitration

