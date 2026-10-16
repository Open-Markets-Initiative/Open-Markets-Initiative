## BinanceSpot Market Data: Binance WebSocket Market Streams

WebSocket market data streams from Binance spot publishing trades, aggregate trades, klines, tickers, best bid and offer, partial book depth and diff depth updates. A raw stream connection (/ws/name) receives each stream's payload, a combined stream connection (/stream?streams=) receives it wrapped as {"stream": name, "data": payload}. The trade, best bid and ask and depth streams are also carried in Sbe on stream-sbe.binance.com, which needs an Ed25519 API key.

### Transport

WebSocket frames: on stream.binance.com ports 9443 and 443 one json message per text frame; on stream-sbe.binance.com one Sbe message per binary frame, with json control messages in text frames.

