## NsmEquities Flite: Nasdaq NSM Equities Fix Lite order entry

Fix Lite (Flite) order entry for Nasdaq Stock Market: a subset of Financial Information eXchange (Fix) 4.2 used to enter, replace and cancel orders and receive execution reports, cancel rejects and start and end of day system events.

### Transport

Tcp for a persistent authenticated Fix 4.2 session with standard sequence-number recovery; one Flite account can be bound to several parallel Flite instances for fault redundancy, with one active connection at a time, and a port can be configured to cancel open orders on disconnect.

