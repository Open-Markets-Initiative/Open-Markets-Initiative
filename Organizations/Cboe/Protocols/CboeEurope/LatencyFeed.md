## CboeEurope Latency Feed: Cboe Europe matching engine latency statistics

Cboe Europe Multicast Latency Feed publishing order to quote latency statistics (count, minimum, maximum, average, standard deviation, mode and percentiles) for each matching engine unit every 15 seconds during market hours.

### Overview

The Multicast Latency Feed lets participants monitor matching engine unit performance. Each Latency Stat message carries one measurement (order to quote) for one matching unit over a Begin Time to End Time window, with the latency metrics as 8 byte little endian doubles in seconds.

### Transport

Udp multicast via the Cboe Sequenced Unit Header from a single multicast group; dropped messages are not recoverable.

### Key Characteristics

- **Latency statistics** - Order to quote latency per matching engine unit
- **Multicast delivery** - One multicast group for all units, no gap recovery

