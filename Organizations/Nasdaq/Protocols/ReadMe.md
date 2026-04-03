## Nasdaq Protocols

Protocol specifications for Nasdaq exchanges and markets. Market data uses Itch encoding over MoldUdp transport and order entry uses Ouch over SoupBinTcp sessions.

### Exchanges

| Exchange | Description |
| --- | --- |
| [NsmEquities](NsmEquities) | Nasdaq Stock Market equities |
| [BxEquities](BxEquities) | Nasdaq Bx equities |
| [PsxEquities](PsxEquities) | Nasdaq Psx equities |
| [NtxEquities](NtxEquities) | Nasdaq Ntx equities |
| [BxOptions](BxOptions) | Nasdaq Bx options |
| [IseOptions](IseOptions) | Nasdaq Ise options |
| [NomOptions](NomOptions) | Nasdaq Options Market |
| [PhlxOptions](PhlxOptions) | Nasdaq Phlx options |

### Transport and Session

| Protocol | Type | Description |
| --- | --- | --- |
| [MoldUdp](MoldUdp.md) | Transport | Udp multicast session and sequencing layer |
| [SoupBinTcp](SoupBinTcp.md) | Session | Tcp session management layer |

## Specifications

Protocol schema definitions are available in the [Specifications](../Specifications) directory.
