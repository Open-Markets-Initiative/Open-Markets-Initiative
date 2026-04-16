## CboeEurope Trf Order Entry: Cboe Europe Trf Trade Report Submission

Order entry protocol for submitting trade reports to the Cboe Europe Equities trade report facility.

### Overview

Trf Order Entry is the Cboe Binary Order Entry variant used to submit trade reports to the Cboe Europe Equities trade report facility. It is the interface through which off-exchange trades are reported for publication to consolidated tape and regulatory reporting, covering trade submission, modification, cancellation, and correction.

The protocol runs over Tcp with the Boe session layer providing authentication, sequence tracking, and recovery. Submitted trade reports are acknowledged back to the submitter with status messages indicating acceptance, rejection, or publication timing.

### Transport

Tcp via the Cboe Binary Order Entry (Boe) session layer for persistent authenticated order flow with sequence tracking, heartbeats, and reliable recovery.

### Key Characteristics

- **Trade report submission** - Off-exchange trade reporting to the Trf
- **Cboe Boe** - Native Cboe Binary Order Entry protocol
- **Trade lifecycle** - Submit, modify, cancel, and correction messages
- **Session based** - Persistent authenticated Tcp session per reporting firm
- **Acknowledgements** - Status messages for each submission

