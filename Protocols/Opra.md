## Opra: Siac Consolidated Options Market Data Feed

Consolidated options market data feed operated by Siac on behalf of the Options Price Reporting Authority publishing quote and trade messages for all listed US options.

OPRA is the Options Price Reporting Authority feed, the SIAC-operated consolidated US options market data distribution spanning all listed options venues.

### Overview

Opra is the consolidated options market data feed for the US listed options industry, operated by the Securities Industry Automation Corporation (Siac) on behalf of the Options Price Reporting Authority. It aggregates quote and trade events from every reporting US options exchange and redistributes them to data vendors, broker-dealers, and end subscribers as a single consolidated stream.

The feed is distributed over Ip multicast across a large number of channels partitioned by symbol range to spread the options message volume across manageable slices. Opra carries quote updates, trade reports, open interest, end-of-day settlement prices, and administrative messages for the full universe of listed options contracts, with a companion Tcp recipient re-request service available for gap recovery.

### Transport

Udp multicast across many channels partitioned by symbol range, carrying sequenced binary quote and trade messages from all reporting options exchanges. Tcp for the Opra recipient re-request service used by subscribers to recover messages missed on the multicast feed.

### Key Characteristics

- **Consolidated options feed** - All listed US options quotes and trades in one stream
- **Multi-exchange source** - Aggregates data from every reporting options exchange
- **Multicast delivery** - Udp multicast across many channels partitioned by symbol range
- **Quote and trade messages** - Full quote and trade event types for every contract
- **Open interest and settlement** - End-of-day open interest and settlement prices
- **Re-request service** - Tcp recipient service for gap recovery of missed messages
- **Industry utility** - Operated by Siac on behalf of the Opra participants

