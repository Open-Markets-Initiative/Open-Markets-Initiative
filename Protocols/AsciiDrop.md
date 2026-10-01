## AsciiDrop: Nasdaq native DROP line format (fixed length, comma delimited ascii)

Line-oriented ascii format of the native Nasdaq DROP drop-copy feeds of the Nasdaq Stock Market, BX, Nasdaq Texas and PSX. Each order event (accept, execution, cancel, break, replace and later correction and modify) is one fixed length, comma delimited printable line opening with its time stamp and a one character type, delivered over a bare TCP socket in the early editions and framed by SoupTCP in the later ones.

### Overview

DROP delivers a real-time, read-only copy of the activity of the orders entered by one or more subscriber firms or ports, typically for clearing firms tracking their correspondents or firms monitoring several access points for risk management. It does not accept orders.

Every event uses the same fixed line layout; the type character says which event the line reports, and some fields change meaning with it (the match number of an execution is the time in force of other events, the liquidity code of an execution is the cancel reason of a cancel). The layout grew by edition: wider reference and match numbers, a replaced token, capacity, an eight character symbol, reference price, ISO, display, BBO weighting and minimum quantity fields.

### Transport

Bare TCP socket: after a password line (optionally followed by a comma and the line number to resume from) the host sends CR/LF terminated lines, an empty line marking the end of the trading day. Used by DROP 1.00 to 2.10 and BX DROP 2.00 and 2.10. SoupTCP (or SoupBinTCP) session carrying each line as a sequenced message. Used by DROP 2.20 and later and by the PSX and Nasdaq Texas editions.

### Key Characteristics

- **Line-oriented ASCII** - Fixed length, comma delimited printable lines, one event per line
- **Drop copy** - Read-only copy of order activity for authorized firms and ports
- **Line number recovery** - A reconnecting client may name the line number to resume from on its login line

