## Spin: Cboe Pitch Spin Server

Tcp replay service that delivers a full order-book snapshot ("spin image") for a Cboe Pitch multicast feed, plus symbol-definition (instrument) images. Clients use the Spin Server to initialize or reinitialize state before joining the live multicast stream.

### Transport

Tcp session in which the client logs in, requests a spin (order-book snapshot) or instrument-definition image by sequence number, and receives the full replay stream followed by a completion marker.

