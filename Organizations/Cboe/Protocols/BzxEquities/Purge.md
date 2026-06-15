## BzxEquities Purge: Cboe Bzx Equities Fix purge

Financial Information eXchange (Fix) purge port protocol for Cboe Bzx Equities, providing mass-cancel of resting orders and, where supported, cross-port order amend, with purge and amend acknowledgement and reject responses.

### Overview

The Purge port is a dedicated Fix session that lets a member mass-cancel resting orders on Cboe Bzx Equities (Purge Request) and receive Purge Acknowledgement and Purge Reject responses.

Where supported, the port also amends orders entered on other order entry ports of the same participant (Amend Request, reusing the Order Cancel/Replace layout), answered by Amend Acknowledgement and Amend Reject.

### Transport

Tcp Fix session per member with sequence tracking, heartbeats, and resend-based recovery.

### Key Characteristics

- **Fix** - Tag-value purge port
- **Mass cancel** - Purge Request to cancel resting orders in bulk
- **Dedicated session** - Separate Fix session from the order entry port

