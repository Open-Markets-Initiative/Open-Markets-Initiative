## OkxDigital Market Data: Okx WebSocket Market Data

WebSocket market data from Okx publishing best bid and offer, tick by tick level 2 and enhanced liquidity books with exponent updates, trades and depth snapshots. The same feed is carried two ways: Json on /ws/v5/public and Sbe on /ws/v5/public-sbe.

### Transport

WebSocket frames on the Okx market data service: opcode 1 carries Json text, opcode 2 one Sbe message per frame.

