## Wats: Warsaw Automated Trading System

The binary encoding of the GPW WATS trading platform, which replaced the NYSE Technologies Universal Trading Platform at the Warsaw Stock Exchange on 5 October 2026. Little endian fixed layout messages, each opening with a header stating its own length, 42 bytes on the market data feeds and 24 on the native order gateway, with implied decimal places, Unix nanosecond timestamps and ChaCha20 encryption of named market data fields. The publisher states the message set in machine readable schemas, market_data.json for market data and trading_port.json for the native order gateway.

