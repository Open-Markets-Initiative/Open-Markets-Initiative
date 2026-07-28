## HkexDerivatives Full Tick Refresh: Orion Market Data Derivatives FullTick Refresh

UDP multicast refresh (snapshot recovery) service for the OMD-D FullTick product. Structurally identical to the real-time channel but publishes state snapshots rather than event streams, letting a late-joining client rebuild current book and reference state.

### Transport

Udp multicast refresh channel publishing periodic state snapshots.

