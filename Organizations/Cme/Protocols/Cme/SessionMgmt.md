## Session Mgmt: Cme Mdp Session Recovery Service

Tcp session management protocol used by Cme market data subscribers to perform recovery operations including market recovery, instrument definition, and snapshot recovery.

### Overview

Cme Session Management is the Tcp-based session recovery service that complements the Mdp3 multicast market data feed. It allows subscribers to request market recovery messages for ranges missed on the multicast feed, instrument definition snapshots for specific securities, and full book snapshots for mid-day initialisation.

The protocol uses Sbe messages consistent with the Mdp3 wire format so that clients can share decoder infrastructure. Session management endpoints are provided at multiple Cme data centers to give subscribers resilient access to the recovery services.

### Transport

Tcp for authenticated session management requests including market recovery, instrument definition requests, and snapshot subscribe requests.

### Key Characteristics

- **Sbe encoded** - Consistent with Mdp3 market data wire format
- **Recovery services** - Market, instrument, and snapshot recovery
- **Session based** - Authenticated Tcp session per subscriber
- **Shared with Mdp3** - Complementary to the multicast market data feed
- **Multi-region** - Endpoints across Cme data centers for resilience

