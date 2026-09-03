## Eti: Enhanced Trading Interface

Bse's binary order entry interface, carrying orders, quotes, and the resulting execution and trade notifications over a session oriented Tcp connection. It follows Fix 5.0 SP2 semantics expressed as fixed length little endian layouts selected by Template Id, and is the interactive counterpart to the Eobi and Emdi market data feeds.

### Overview

Bse Eti is a licensed deployment of the T7 Enhanced Trading Interface and inherits its message model. Application messages follow Fix 5.0 SP2 semantics including approved extension packs, with user defined fields and messages added where the standard leaves gaps. Parties are identified by individual user defined fields rather than repeating groups, and every rejection is reported through the standard Reject message.

Logon is a four step procedure. The participant opens a Tls 1.3 connection to a connection gateway and sends a Connection Gateway Request; the response names the primary and secondary application gateways and is then closed. The participant has one hundred and twenty seconds to open a Tcp connection to an application gateway, where a Session Registration Request must be the first message, followed by Session Logon, followed by one or more User Logon messages. Any other opening message is rejected and the connection dropped.

All communication is encrypted. The Connection Gateway Response carries a thirty two byte key and a sixteen byte initialisation vector, and from the Session Registration Response onward every message body is Aes 256 Gcm ciphertext. Only the message body is encrypted; the message header stays in the clear, so Body Len continues to frame the stream and Template Id continues to name the layout even when the body cannot be read. The Connection Gateway Request is protected by Tls instead, and the Session Registration Request is the one message sent unencrypted on the gateway connection.

Each message opens with a header naming its own length and layout. Bse names the header from the exchange's point of view, so a message carrying Message Header In travels in to the exchange and one carrying Message Header Out travels out to the participant, which is how the direction of every layout is read from the schema rather than configured.

Sessions are either low frequency or high frequency, and the session is dropped on Tcp disconnect, on three consecutive missed heartbeats, or when the reject and disconnect limit is exceeded. The system forces a logout overnight.

### Transport

One Tcp connection per session to an assigned application gateway, carrying both directions of the conversation, preceded by a Tls 1.3 exchange with a connection gateway that hands back the gateway address and the session encryption material.

### Key Characteristics

- **Session oriented** - A single Tcp connection to an assigned application gateway carries both directions of the conversation for the life of the session
- **Fixed length binary** - Little endian fixed width layouts selected by Template Id, with explicit padding fields holding eight byte alignment
- **Fix derived** - Application messages follow Fix 5.0 SP2 semantics with user defined fields replacing repeating groups for party identification
- **Encrypted body** - Message bodies are Aes 256 Gcm ciphertext from the Session Registration Request onward while the message header remains in the clear
- **Gateway indirection** - A Tls protected connection gateway assigns the application gateway and issues the session key and initialisation vector before trading begins
- **Bidirectional layouts** - The header component names the sending side, so each layout is bound to the participant or the exchange rather than shared

