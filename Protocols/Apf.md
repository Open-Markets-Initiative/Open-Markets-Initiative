## Apf: Cboe Europe Ascii Price Feed

ASCII-based Last Sale feed format historically used by Cboe Europe for trade dissemination, superseded by the Pitch binary protocol on current feeds.

### Transport

Apf is distributed over UDP multicast. Each message is a pipe-delimited ASCII record terminated by a line feed.

### Key Characteristics

- **ASCII encoding** - Human-readable pipe-delimited records rather than binary fixed-length messages
- **Last Sale feed** - Trade dissemination feed for Cboe Europe cash markets

