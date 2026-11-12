## BmvMarketData Snapshot: Bmv Market Data Snapshot

Tcp snapshots of a multicast group: instrument catalogs, active orders, price levels, best offers or recent trades, after a login.

### Transport

Tcp, one request at a time after a Login; requests carry a one byte length, responses and snapshot messages the INTRA Multicast Header.

