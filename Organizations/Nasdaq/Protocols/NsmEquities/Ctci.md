## NsmEquities Ctci: Nasdaq NSM Equities Computer to Computer Interface (CTCI)

Computer to Computer Interface (CTCI) for Nasdaq Stock Market: a connection to the Nasdaq Message Switch carrying text messages for order entry, ACES and risk management, plus station supervisory and administrative messages.

### Transport

Tcp/Ip sessions to the Nasdaq Message Switch: each message in a length prefixed envelope with a logical channel, and logon, heartbeat, flow control and logical channel control messages on channel zero; the message text could also be exchanged through IBM WebSphere MQ.

