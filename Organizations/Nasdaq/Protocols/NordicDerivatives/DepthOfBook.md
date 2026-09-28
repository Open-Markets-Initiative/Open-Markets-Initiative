## NordicDerivatives Depth Of Book: Nasdaq Nordic Genium INET ITCH and GLIMPSE

Market by order feed of the Nasdaq Nordic Genium INET platform, publishing every displayable order and its executions, trades in non-displayed orders, order book and combination order book directories, the tick size table, order book states and equilibrium prices, with a GLIMPSE snapshot service to join it mid session.

### Overview

Genium INET Itch is the "main" Itch feed of the Nasdaq Nordic derivatives and commodities markets that run on the Genium INET platform, beside the Itch-like Auxiliary Market Data feed. It gives the full order depth order by order, with market participant attribution where the marketplace uses it, and the trades of non-displayed orders; reported trades are not part of it.

Order IDs are unique only per order book and side, and orders are ranked by an explicit order book position rather than by time, so a reader builds the book by inserting and removing at positions. Market by order dissemination may be switched off during call auctions, in which case every order is deleted from the view before the auction and added back after it.

### Transport

Itch over MoldUDP64 multicast; Genium INET Nordics provides Itch only as multicast, from two sites, with a rerequest service for missed packets. GLIMPSE over SoupBinTcp, a point to point snapshot of the order books ending with the Itch sequence number to join the multicast from.

### Key Characteristics

- **Market by order** - Every displayable order with its position in the book
- **Combination order books** - Standard and tailor made combinations with up to four legs
- **Split timestamps** - A Seconds message carries the second, each message the nanoseconds within it
- **Snapshot recovery** - GLIMPSE replays the book and gives the Itch sequence number to resume from

