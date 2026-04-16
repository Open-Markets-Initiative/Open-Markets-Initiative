## Tms: Tmx Montreal Exchange Trade Management System

Trade management interface for submitting, modifying, and verifying trade reports on the Tmx Montreal Exchange.

### Overview

Tms is the Tmx Montreal Exchange Trade Management System, providing members with an interface for submitting trade reports, modifying existing reports, and verifying trade state. It handles off-exchange trades that need to be reported to Mx for publication and clearing.

### Transport

Tcp for authenticated trade management sessions carrying trade submission, modification, and acknowledgement messages.

### Key Characteristics

- **Trade reporting** - Off-exchange trade submission to Mx
- **Montreal Exchange** - Tmx Mx trade management
- **Session based** - Authenticated Tcp session per member
- **Trade lifecycle** - Submit, modify, and verify trade messages
- **Acknowledgements** - Status messages for each submission

