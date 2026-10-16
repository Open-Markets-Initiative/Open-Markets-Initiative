## BinanceUs Market Data: Binance.US WebSocket Streams

WebSocket market data streams from Binance.US publishing trades, aggregate trades, klines, tickers, best bid and offer, partial book depth and diff depth updates. A raw stream connection (/ws/name) receives each stream's payload, a combined stream connection (/stream?streams=) receives it wrapped as {"stream": name, "data": payload}. The streams follow Binance spot's, but Binance.US documents them separately and they have diverged.

### Transport

WebSocket text frames on stream.binance.us port 9443, one json message per frame.

