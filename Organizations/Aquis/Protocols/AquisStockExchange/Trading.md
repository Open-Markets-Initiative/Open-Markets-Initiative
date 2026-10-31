## AquisStockExchange Trading: Aquis Stock Exchange FIX 4.4 Trading Specification v2.1

Fix 4.4 protocol for Aquis Stock Exchange members: trade reporting by Trade Capture Report and market maker quoting by Mass Quote and Quote Cancel, with their acknowledgements.

### Transport

Tcp sessions tied to an agreed IP address and port, with no password; sequence numbers reset to one overnight, and open quotes are cancelled when a session ends unless the member asks otherwise.

