## Spectra Fut Info Incremental: SIMBA Spectra Futures Instrument Incremental

Real-time changes to the futures instrument set and to session state, the companion to the looping FUT-INFO replay stream: per-instrument trading status, the mass status packet that restates many instruments at once, group-level halts and trade modes, trading session transitions and discrete auction windows. A subscriber accumulates these while reading the replay stream and applies them over the instrument list it builds.

### Transport

Udp multicast on the FUT-INFO groups, duplicated as an A and a B group, carrying instrument and session status changes as they happen.

### Key Characteristics

- **Status changes** - Per-instrument, mass and group-level trading status updates
- **Session transitions** - Trading session open and close with the session type
- **Discrete auction windows** - Opening auction start and the interval it may complete in
- **Simple Binary Encoding** - Fix messages encoded to the Sbe version 1 standard against a published schema
- **Transaction timing** - An incremental packet header states when matching began on the change
- **Paired multicast streams** - Every stream is broadcast twice on separate groups for arbitration

