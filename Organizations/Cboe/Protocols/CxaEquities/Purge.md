## CxaEquities Purge: Cboe Australia Fix purge-amend port

Financial Information eXchange (Fix 4.2) purge-amend port protocol for Cboe Australia, providing mass-cancel (purge) and cross-port order amend operations over a dedicated Fix session, with purge and amend acknowledgement and reject responses.

### Overview

The Purge-Amend port is a dedicated Fix session that lets a member mass-cancel resting orders (Purge Request) and amend orders entered on other Fix or Boe order entry ports within the same participant (Amend Request, which reuses the Order Cancel/Replace Request layout).

Responses comprise Purge Acknowledgement, Purge Reject, Amend Acknowledgement, and Amend Reject. The port performing an amend receives an Execution Report with Replaced (150=5); the originating port receives Restated (150=D).

### Transport

Dedicated Tcp Fix purge-amend session per member.

### Key Characteristics

- **Fix 4.2** - Tag-value purge-amend port
- **Mass cancel** - Purge Request to cancel resting orders in bulk
- **Cross-port amend** - Amend orders entered on other ports of the same participant
- **Dedicated session** - Separate Fix session from the order entry port

