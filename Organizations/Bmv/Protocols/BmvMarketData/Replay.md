## BmvMarketData Replay: Bmv Market Data Replay

Tcp replay of the last 50,000 messages published on a multicast group, after a login.

### Transport

Tcp, one request at a time after a Login; requests carry a one byte length, responses and replayed messages the INTRA Multicast Header.

