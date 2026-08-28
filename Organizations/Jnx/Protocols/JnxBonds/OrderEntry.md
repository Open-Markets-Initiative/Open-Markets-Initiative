## JnxBonds Order Entry: Japannext Fix Trading Specification Bonds

Financial Information eXchange encoding of the Japannext order entry interface for bonds, used by participants to submit, amend and cancel orders on the Japannext Pts bonds venue and to receive execution reports, cancel rejects and trading session status over a Fix session.

### Overview

Japannext offers order entry over both Fix and Ouch. The Fix interface carries the fuller order and execution vocabulary, while Ouch is the lighter binary path for latency sensitive participants. Both reach the same matching engine.

The bonds interface differs from the equities one in what a bond order needs: a price type describing how the price is expressed, and the contra broker reported on each fill. The Japanese cash and margin fields the equities interface carries have no bond equivalent.

### Transport

Tcp for reliable ordered delivery over a persistent Fix session with logon, heartbeat and sequence based recovery.

### Key Characteristics

- **Bonds order entry** - Order submission, amendment and cancellation for the Japannext Pts bonds venue
- **Price type** - How the price of the bond is expressed
- **Contra broker reporting** - The firm on the other side is named on each fill

